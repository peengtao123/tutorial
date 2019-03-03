```shell
wget https://github.com/kubernetes/kubernetes/releases/download/v1.1.1/kubernetes.tar.gz

etcd -name etcd -data-dir /var/lib/etcd/ -listen-client-urls http://0.0.0.0:2379,http://0.0.0.0:4001 -advertise-client-urls http://0.0.0.0:2379,http://0.0.0.0:4001 >> /var/log/etcd.log 2>&1 &


kube-apiserver          --logtostderr=true --v=0 --etcd_servers=http://spark:4001 --insecure-bind-address=0.0.0.0 --insecure-port=8080 --service-cluster-ip-range=10.254.0.0/16 >> /var/log/kube-apiserver.log 2>&1 &


kube-controller-manager --logtostderr=true --v=0 --master=http://spark:8080 >> /var/log/kube-controller-manager.log 2>&1 &


kube-scheduler          --logtostderr=true --v=0 --master=http://spark:8080 >> /var/log/kube-scheduler.log 2>&1 &


kube-proxy              --logtostderr=true --v=0 --master=http://spark:8080 >> /var/log/kube-proxy.log 2>&1 &


kubelet                 --logtostderr=true --v=0 --config=/etc/kubernetes/manifests --address=0.0.0.0 --api-servers=http://spark:8080 >> /var/log/kubelet.log 2>&1 &
```