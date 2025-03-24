# Fake Shop


## Variável de Ambiente
DB_HOST	=> Host do banco de dados PostgreSQL.

DB_USER => Nome do usuário do banco de dados PostgreSQL.

DB_PASSWORD	=> Senha do usuário do banco de dados PostgreSQL.

DB_NAME	=>	Nome do banco de dados PostgreSQL.

DB_PORT	=>	Porta de conexão com o banco de dados PostgreSQL.

kubectl apply -f k8s/deployment_local.yaml 
kubectl delete -f k8s/deployment_local.yaml 

k3d cluster create --servers 3 --agents 3
k3d cluster create --servers 3 --agents 3 -p "5000:30000@loadbalancer"
k3d cluster delete

kubectl port-forward service/fakeshop 5000:5000
kubectl get pod
kubectl get service
kubectl get deployment
kubectl get replicaset
kubectl get all
kubectl get pod -o wide


kubectl rollout history deployment fakeshop

kubectl rollout undo deployment fakeshop

comando senha grafana:

kubectl get secret --namespace default grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

flask_http_request_duration_seconds_count{app="fakeshop", path="/"}

