#VuFind 2虛擬應用範本#

這是VuFind 2的OpenVZ虛擬應用範本(Virtual Application Template)保存庫

[下載VuFind 2虛擬應用範本](http://cloud-disk-2013.dlll.nccu.edu.tw/public.php?service=files&t=abc16758e8b8c4c91538830a4016565b)

*這是Open VZ的虛擬應用範本，請不要解壓縮，可直接使用。*

##架設##

架設方式：[Proxmox VE 3安裝與建立OpenVZ虛擬機器](http://pulipuli.blogspot.tw/2013/07/proxmox-ve-3openvz.html)

架設起來之後，連線方式如下：( **[vufind]**是該主機的網址 )
- http://[vufind]/
VuFind主畫面
- https://[vufind]/
Turnkey Linux伺服器管理畫面：Web Shell (console), Webmin, PHPMyAdmin, Apache Solr

##設定##

###Koha設定###
- 修改 /usr/local/vufind2/local/config/vufind/Koha.ini
- 執行 ~/vufind-restart.sh

###OAI-PMH設定###
- 修改 /usr/local/vufind2/harvest/oai.php
- 執行 ~/harvest_oai.sh

###DataImport設定###
- 修改 /usr/local/vufind2/solr/biblio/conf/dataimport-config-mysql.xml
- 執行 ~/dataimport_full.sh

##MySQL資料庫##
帳號與密碼：
root / password

##自動排程工作##
*(詳情請看 crontab -e)*

- 每天早上1點，匯入Apache Solr Data Import
- 每天早上3點，匯入OAI-PMH
- 每天早上5點，執行Apache Solr最佳化 (optimize)

##其他指令##
- ~/clean_vufind.sh
把資料全部清空，但是設定檔案不會還原，請注意。

------
##其他工具##
- Markup Editor: [StackEdit](https://stackedit.io/)
- 虛擬應用範本的基礎：[Turnkey Linux: LAMP Stack](http://www.turnkeylinux.org/lampstack)
