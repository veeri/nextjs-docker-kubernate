Kubernetes runs inside Minikube, not on your Mac.
below command copies a Docker image from your Mac into Minikube’s Docker environment, so Kubernetes can use it.

minikube image load nextjs-app:latest


    What minikube image load does
    Before
    Mac Docker      → has image
    Minikube Docker → does NOT

    After
    Mac Docker      → has image
    Minikube Docker → ALSO has image ✅

So Kubernetes can start the pod
