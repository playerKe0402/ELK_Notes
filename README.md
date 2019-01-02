# ELK (Elasticsearch , Logstash , Kibana)

## 環境
Oracle Linux，其建基於Red Hat Enterprise Linux

## 安裝過程


## 使用過的指令
### 通用
從 /from 將 test 檔案移動到 /to
```
$ mv /from/test /to
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
[RHEL / CentOS 列出及查詢已安裝的套件](https://www.phpini.com/linux/rhel-centos-list-search-installed-packages)

[YUM 安裝/更新/移除套件指令](https://www.phpini.com/linux/yum-install-remove-update-package)

[mv — 移動或重新命名 (rename)檔案及目錄指令](https://www.phpini.com/linux/mv-move-rename-file-directory-command)
