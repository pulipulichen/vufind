這是VuFind 2的OpenVZ虛擬應用範本(Virtual Application Template)保存庫

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

- 每天早上1點，自動匯入Apache Solr Data Import
- 每天早上3點，自動匯入OAI-PMH

------
##其他工具##
- Markup Editor: [StackEdit](https://stackedit.io/)
