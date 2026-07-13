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

