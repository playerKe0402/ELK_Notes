# ELK (Elasticsearch , Logstash , Kibana)

## 環境
Oracle Linux，其建基於Red Hat Enterprise Linux

## 安裝過程
### Elasticsearch 安裝
下載 JAVA([JRE](https://www.oracle.com/technetwork/java/javase/downloads/index.html))

安裝 JRE
```
$ rpm -ivh jre-*.rpm
```
下載 [Elasticsearch](https://www.elastic.co/downloads/elasticsearch)

安裝 Elasticsearch
```
$ rpm -ivh elasticsearch-*.rpm
```
啟動 Elasticsearch
```
$ systemctl start elasticsearch
```
查看狀態
```
systemctl status elasticsearch
$ curl "http://localhost:9200/_cat/nodes"
```
設定記憶體
```
$ vim /etc/elasticsearch/jvm.options
```

記憶體越大，查詢速度越快。使用記憶體有兩個限制 :

- 最高只能設定為系統的 50%。例：系統 8GB，Elasticsearch 只能設定 4GB

- 不能超過 32GB

設定 Elasticsearch 記憶體使用上限(Xmx)及下限(Xms)
```
-Xms1g
-Xmx1g
```
設定 Elasticsearch 的 IP 及 Port
```
$ vim /etc/elasticsearch/elasticsearch.yml
```
綁定所有 IP
```
network.host: 0.0.0.0
```
綁定 Port，預設 9200
```
http.port: 9200
```
重新啟動
```
$ systemctl start elasticsearch
```
防火牆完全關閉
```
$ systemctl stop firewalld
$ systemctl disable firewalld
```
增加防火牆規則
```
$ firewall-cmd --add-port=9200/tcp --permanent
$ firewall-cmd --reload
```


###

## 使用過的指令
### 通用
從 /from 將 test 檔案移動到 /to
```
$ mv /from/test /to
```
解壓縮，例如解壓縮elasticsearch-6.1.3.tar.gz
```
$ tar -zxvf elasticsearch-6.1.3.tar.gz
```
將整個 test 目錄刪除而不會先警告
```
$ rm -rf test/
```
### RPM
列出系統內所有已安裝的套件清單

q : query(詢問)

a : 列出所有安裝套件
```
 $ rpm -qa
```
查詢某一個套件，搭配grep指令，例如想查詢包括 kibana 關鍵字的套件
```
 $ rpm -qa | grep kibana
```
### YUM
列出系統內所有已安裝的套件清單
```
 $ yum list installed
```
查詢某一個套件，搭配grep指令，例如想查詢包括 kibana 關鍵字的套件
```
 $ yum list installed | grep kibana
```
安裝套件，例如安裝 kibana 套件
```
 $ yum install kibana
```
移除套件，例如移除 kibana 套件
```
 $ yum remove kibana
```
## Reference
[ELK 教學 - 從無到有安裝 ELK (CentOS/Red Hat)](https://blog.johnwu.cc/article/how-to-install-elasticsearch-logstash-and-kibana-elk-stack-on-centos-red-hat.html)

[RHEL / CentOS 列出及查詢已安裝的套件](https://www.phpini.com/linux/rhel-centos-list-search-installed-packages)

[YUM 安裝/更新/移除套件指令](https://www.phpini.com/linux/yum-install-remove-update-package)

[mv — 移動或重新命名 (rename)檔案及目錄指令](https://www.phpini.com/linux/mv-move-rename-file-directory-command)

[rm – 刪除檔案及目錄指令](https://www.phpini.com/linux/rm-delete-files-directory-command)
