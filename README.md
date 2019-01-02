# ELK (Elasticsearch , Logstash , Kibana)

## 環境
Oracle Linux，其建基於Red Hat Enterprise Linux

## 使用過的指令
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

## Reference
[RHEL / CentOS 列出及查詢已安裝的套件](https://www.phpini.com/linux/rhel-centos-list-search-installed-packages)
