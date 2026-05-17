![[Pasted image 20260516000436.png]]

- The dockerfile is adding everything that I created in the row 8, this takes a lot of time to load every time.
- The row 11 reinstall everytime because it is after the copy activity. 

### Why to use --no-cache-dir?

https://stackoverflow.com/questions/45594707/what-is-pips-no-cache-dir-good-for

-  Reduces docker image size if python dependencies are used in dockerfile.

### How to keep the app running 24/7 in the droplet: 

docker run -d \ --restart always \ --name arimura-prod \ -p 5000:5000 \ --env-file /opt/arimura/.env.prod \ arimura-cj:latest

- --restart always flag in the running command

Analogy: 
- GitHub Actions = the kitchen that cooks the meal (builds the image)
- DigitalOcean Registry = the pass where the plate sits ready
- Droplet = the waiter that picks up the plate and serves it to Curitiba

### Observations regarding dockerfile

problem: 

Before: 
- name: Push image to registry
        run: echo "${{ secrets.DIGITALOCEAN_ACCESS_TOKEN }}"  docker login registry.digitalocean.com -u ${{ secrets.DIGITALOCEAN_ACCESS_TOKEN }} --password-stdin
          docker push ${{ vars.REGISTRY }}/arimura-cj:latest


- name: Push image to registry
        run: |
          echo "${{ secrets.DIGITALOCEAN_ACCESS_TOKEN }}" | docker login registry.digitalocean.com -u ${{ secrets.DIGITALOCEAN_ACCESS_TOKEN }} --password-stdin
          docker push ${{ vars.REGISTRY }}/arimura-cj:latest

The `|` tells YAML "everything indented below me is a multi-line script". Without it, YAML reads only the first line as the command.
