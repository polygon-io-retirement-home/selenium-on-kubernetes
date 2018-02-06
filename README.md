

# Selenium Hub / Grid on Kubernetes
Kube files for deploying Selenium Hub ( Selenium Grid ) and Nodes ( Chrome & Firefox ) on Kubernetes

This should be everything needed to get up and running with a selenium grid cluster in k8s.

These must be run in order

```bash
	# Deploy the namespace:
	kubectl apply -f selenium.namespace.yml

	# Deploy the Hub node:
	kubectl apply -f selenium-hub.deployment.yml

	# Deploy hub service so nodes can talk to hub node:
	kubectl apply -f selenium-hub.service.yml

	# If you want Chrome nodes:
	kubectl apply -f selenium-chrome.deployment.yml

	# If you want Firefox nodes:
	kubectl apply -f selenium-firefox.deployment.yml
```

Now you should have a hub node, and 1 chrome and 1 firefox node running.

If you need more nodes, you can scale them like so:

```bash
	kubectl scale --replicas=3 -f selenium-chrome.deployment.yml
```

