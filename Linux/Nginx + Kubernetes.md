- High performance, open source web server software.

#### LoadBalancer 
- creates an external resource.

#### Commands to review:

Check if the service exists:
 -  kubectl get pods 
 - kubectl get services 

Check pods logs:
- kubectl logs {pod name}

Check that the service is created internally by printing the environment variable for it:
- kubectl exec {pod name} -- printenv GUESTBOOK_SERVICE_HOST

Check the pod description:
- kubectl describe pod {pod name}.

Give an instance if of the pod or SSH to it and run Docker to verify the container running:
- sudo iptables-save

### Challenge SadServers

Link: https://sadservers.com/scenario/bilbao

To solve this challenge is needed the comprehension of some concepts: 

![[Pasted image 20260721162131.png]]

1) What are nodes? 
	- A worker machine is Kubernetes and may be either a virtual or a physical machine, depending on the cluster. 
	- They work as "Mini VM" with a specific amount of CPU, Memory/RAM.
	- If one node is 100% consumed, then they start to consume from another node. 
	- A combination of nodes are called Cluster. 

2) What are pods?
	- Pod are the inside of nodes, which organizes the unit that consumes and organizes the CPU/Memory to run something. 
	- Provides the container it own IP Address.
	- Everything that exists in the same pod, must never be separated. 

3) What are containers? 
	- It's where the application is running. It has all the things necessary to run the application. 


Problem: 
![[Pasted image 20260721163207.png]]

1) Identify the problem: 
	- Refused: something is listening on the host but not on that port, or the process isn't running.
	- Timed Out: firewall/network is silently dropping packages of the host is unreachable. 

2) verify the .yml file.

3)  Verify nodes
	-  If one has the status NotReady, means that is something off.
	- Then run:
		- kubectl describe node {node-name}
		- Look for the condition: 
		![[Pasted image 20260721165016.png]]
			Here says: **"Kubelet stopped posting node status"** across all conditions means the kubelet on that node has completely stopped communicating with the control plane — it's not a resource issue (CPU/memory/disk), it's that the node has gone silent entirely.
			The node is fairly old: 2y185d, which is better to delete the old one. 
		- kubectl delete node {node-name}
		- The node is declared in the .yml file that needs a SSD. Therefore, we must adjust either the .yml file or the label of the node. I will choose the .yml file here. 
		
4)  Verify pods 
	- Once the nodes are running, we must verify the PODS.
	![[Pasted image 20260721165627.png]]
	Here is pending, which means that is not running. 
	- Understand why the pod is not ready:
		kubectl describe pods {pod name}
![[Pasted image 20260721170156.png]]

Here is the error, in the events block from pod description. This link explain all the possible problems of the FailedScheduling: https://oneuptime.com/blog/post/2026-01-25-debug-failedscheduling-errors/view.
	- Running this command you get a better description of the problem: 
	
```
kubectl get events --field-selector reason=FailedScheduling
```

- Our case if "affinity /selector" problem. 
5) Then we must verify the resources by:

kubectl describe nodes | grep -A 10 "Allocated resources"

kubectl get pod {pod name} -o jsonpath='{.spec.containers[*].resources}'
- This describes exactly the specific problem

Comparing our allocated resources and our .yml we noticed that: 

![[Pasted image 20260721171433.png]]

- The .yml file is calling a node with the label ssd.
- We only have 200m CPU and 140Mi of RAM and our .yml  declares that we are using 2000Mi . 

**Solution**: Drop the 2000 to 200Mi  and comment the "nodeSelector:"and "disk: ssd".  Then restart the kubernetes:
kubectl apply -f manifest.yml

Wait 1 or 2 minutes then run: kubectl get pods, verify if the status changed and then run curl IP-ADDRESS. 
