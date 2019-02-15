# *WebServices*
##### *Simone Franceschini - Davide Sartori - Alessandro Scardino - Marco Tregnaghi*
### 5CI - I.T.I. GUGLIELMO MARCONI - VERONA
###
Installation guide of ***ELK*** (**Elasticsearch**, **Logstash**, **Kibana**) and **FSCrawler** on a Debian machine.

##### [**ELK**](https://www.elastic.co/)
##### [**FSCrawler**](https://github.com/dadoonet/fscrawler)

### **PREREQUISITES**
- A computer with debian installed.
- A internet access for download some content.

### **INSTALLATION GUIDE**
- Check if the latest java is installed in your system with the command `java -version`.
- If Java is not installed, download it from the link in the table that is at the end of this page   and install it. **(Download the 64 bit version, NOT RMP)** .
- Download the `.deb` of ***Logstash*** from the link down below and go to the appropriate folder where it is contained; at the end install it with the command `dpkg -i filename`.
- Download the `.deb` of ***Elasticsearch*** from the link down below and install it as previously described.
- Download the `.deb` of ***Kibana*** from the link down below and install it as previously described.
- Download the `.zip` of ***FSCrawler*** from the link down below and unzip it.
- Start the ***Logstash*** service with the command `service logstash start`.
- Start the ***Elasticsearch*** service with the command `service elasticsearch start` (It will load in a range of 2-6 minutues).
- Start the ***Kibana*** service with the command `service kibana start`.
- Wait a few minutes that all is loaded
- On the browser write `localhost:9200`, if a page is shown, ***Logstash*** is loaded.
- On the browser write `localhost:9600`, if a page is shown, ***Elasticsearch*** is loaded.
- On the browser write `localhost:5601`, if a page is shown, ***Kibana*** is loaded.
- Now we can test if ***FSCrawler*** works.
- With the terminal go in the unzipped folder of ***FSCrawler***, in the `bin` folder.
- Create a test folder with the command `mkdir /tmp/es`.
- Return in the `bin` directory and create a new job with the the command `sh fscrawler test`.
- Create a test file in the folder `/tmp/es` with the command `touch test.txt`.
- Start ***FSCrawler***, in the folder `bin`, with the command `sh fscrwaler test`.
- Open ***Kibana*** on the browser, select `Dev Tools` on the menu on the left, then select `Console`.
- Now in the editor in the first line write this line: `GET test/_search`.
- Inside the parenthesis of the field `term` write this line: `"file.filename": "test.txt"`
-  Now press the play button on the right corner of the editor to run the `GET`.
-  Now on the right you can see the information related to `test.txt`.

###
#### **INSTALLATION TESTED ON DEBIAN 9 x64**

---
###
### **DOWNLOAD**
###

| *SOFTWARE* | *LINK* |
| ------ | ------ |
| **Java** | https://www.java.com/it/download/manual.jsp |
| **Logstash** | https://www.elastic.co/downloads/logstash |
| **Elasticsearch** | https://www.elastic.co/downloads/elasticsearch |
| **Kibana** | https://www.elastic.co/downloads/kibana |
| **FSCrawler** |https://fscrawler.readthedocs.io/en/fscrawler-2.6/installation.html |

###### *Markdown developed with [**Dillinger**](https://dillinger.io/), the Online Markdown Editor.*
