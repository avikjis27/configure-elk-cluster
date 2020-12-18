```
curl -XGET '192.168.50.10:9200/_cluster/health?level=indices&pretty' | head -50
```

```
{
  "cluster_name" : "test-cluster",
  "status" : "green",
  "timed_out" : false,
  "number_of_nodes" : 2,
  "number_of_data_nodes" : 1,
  "active_primary_shards" : 0,
  "active_shards" : 0,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 0,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 0,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 0,
  "active_shards_percent_as_number" : 100.0,
  "indices" : { }
}

```


https://blog.trifork.com/2013/10/24/how-to-avoid-the-split-brain-problem-in-elasticsearch/
https://www.elastic.co/guide/en/elasticsearch/reference/master/modules-discovery-bootstrap-cluster.html
https://www.elastic.co/guide/en/elasticsearch/reference/current/settings.html
https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-node.html
https://www.elastic.co/guide/en/elasticsearch/reference/current/setup.html
https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-network.html
https://www.elastic.co/guide/en/elasticsearch/reference/current/add-elasticsearch-nodes.html
https://blog.sleeplessbeastie.eu/2020/02/29/how-to-prevent-systemd-service-start-operation-from-timing-out/



https://www.elastic.co/blog/getting-started-with-elasticsearch-security





hannel, closing connection Netty4TcpChannel{localAddress=/192.168.50.10:9300, remoteAddress=/192.168.50.11:35194}
[2020-12-05T16:45:37,652][WARN ][o.e.x.c.s.t.n.SecurityNetty4Transport] [master] received plaintext traffic on an encrypted channel, closing connection Netty4TcpChannel{localAddress=/192.168.50.10:9300, remoteAddress=/192.168.50.11:35196}
[2020-12-05T16:45:38,652][WARN ][o.e.x.c.s.t.n.SecurityNetty4Transport] [master] received plaintext traffic on an encrypted channel, closing connection Netty4TcpChannel{localAddress=/192.168.50.10:9300, remoteAddress=/192.168.50.11:35198}
[2020-12-05T16:45:39,658][WARN ][o.e.x.c.s.t.n.SecurityNetty4Transport] [master] received plaintext traffic on an encrypted channel, closing connection Netty4TcpChannel{localAddress=/192.168.50.10:9300, remoteAddress=/192.168.50.11:35200}
[2020-12-05T16:45:40,679][WARN ][o.e.x.c.s.t.n.SecurityNetty4Transport] [master] received plaintext traffic on an encrypted channel, closing connection Netty4TcpChannel{localAddress=/192.168.50.10:9300, remoteAddress=/192.168.50.11:35202}
[2020-12-05T16:45:41,738][WARN ][o.e.x.c.s.t.n

bin/elasticsearch-certutil cert -out config/elastic-certificates.p12 -pass ""

https://www.elastic.co/guide/en/elasticsearch/reference/current/anonymous-access.html

{
  "error" : {
    "root_cause" : [
      {
        "type" : "security_exception",
        "reason" : "missing authentication credentials for REST request [/_cluster/health?level=indices&pretty]",
        "header" : {
          "WWW-Authenticate" : "Basic realm=\"security\" charset=\"UTF-8\""
        }
      }
    ],
    "type" : "security_exception",
    "reason" : "missing authentication credentials for REST request [/_cluster/health?level=indices&pretty]",
    "header" : {
      "WWW-Authenticate" : "Basic realm=\"security\" charset=\"UTF-8\""
    }
  },
  "status" : 401
}


xpack.security.authc:
  anonymous:
    username: anonymous_user
    roles: apm_system, apm_user
    authz_exception: true