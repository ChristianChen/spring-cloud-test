Consul:

install:
Put consul fi

start:
./consul agent -server -ui -bootstrap-expect 1 -data-dir ~/.spring-cloud/consul/data -config-dir ~/.spring-cloud/consul/config

check nodes:
http://localhost:8500/v1/catalog/nodes

web UI:
http://localhost:8500/ui

config:
<code>
acl_token：agent会使用这个token和consul server进行请求
acl_ttl：控制TTL的cache，默认是30s
addresses：一个嵌套对象，可以设置以下key：dns、http、rpc
advertise_addr：等同于-advertise
bootstrap：等同于-bootstrap
bootstrap_expect：等同于-bootstrap-expect
bind_addr：等同于-bind
ca_file：提供CA文件路径，用来检查客户端或者服务端的链接
cert_file：必须和key_file一起
check_update_interval：
client_addr：等同于-client
datacenter：等同于-dc
data_dir：等同于-data-dir
disable_anonymous_signature：在进行更新检查时禁止匿名签名
enable_debug：开启debug模式
enable_syslog：等同于-syslog
encrypt：等同于-encrypt
key_file：提供私钥的路径
leave_on_terminate：默认是false，如果为true，当agent收到一个TERM信号的时候，它会发送leave信息到集群中的其他节点上。
log_level：等同于-log-level node_name:等同于-node
ports：这是一个嵌套对象，可以设置以下key：dns(dns地址：8600)、http(http api地址：8500)、rpc(rpc:8400)、serf_lan(lan port:8301)、serf_wan(wan port:8302)、server(server rpc:8300)
protocol：等同于-protocol
rejoin_after_leave：等同于-rejoin
retry_join：等同于-retry-join
retry_interval：等同于-retry-interval
server：等同于-server
syslog_facility：当enable_syslog被提供后，该参数控制哪个级别的信息被发送，默认Local0
ui_dir：等同于-ui-dir
</code>

