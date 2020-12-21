Deploy ArgoCD: 

<pre><code>

kubectl create namespace argocd
kubectl label namespace argocd istio-injection=enabled
kubectl apply -n argocd -f argocd.yaml

</code></pre>

Deploy ArgoRollouts: 

<pre><code>

kubectl create namespace argo-rollouts
kubectl apply -n argo-rollouts -f argo-rollouts.yaml

</code></pre>