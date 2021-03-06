# Node-RED 存取雲端資料庫(No SQL DB)
目的: Node-RED產生資料，顯示在dashboard，再存到雲端資料庫，資料庫可以查詢，可以刪除，當然可以新增。<br>
參考書籍: [物聯網實作 Node-RED萬物聯網視覺化 陸瑞強 廖裕評](https://books.google.com.tw/books?id=5DFsDwAAQBAJ&printsec=frontcover&hl=zh-TW&source=gbs_ge_summary_r&cad=0#v=onepage&q&f=false)<br>
網路資源: [IBM 雲端平台](https://www.ibm.com/cloud-computing/bluemix/zh-hant)<br>

## 雲端資料庫建立
1. 註冊IBM雲端平台帳號

2. 建立Cloudant NoSQL BD
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/IBM_CloudDB_1.png?raw=true "Cloudant NoSQL BD")

3. 建立temp_humidity資料庫
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/IBM_CloudDB_2.png?raw=true "進入Cloudant NoSQL BD")

4. 完成temp_humidity資料庫<br>
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/IBM_CloudDB_3.png?raw=true "Cloudant Dashboard")

## Node-RED程式
以HTTP POST方式新增資料到資料庫<br>
Node-RED code:
```JSON
[
    {
        "id": "8a8a090e.fb44e8",
        "type": "inject",
        "z": "86bea44.a06ec58",
        "name": "",
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "repeat": "",
        "crontab": "",
        "once": false,
        "onceDelay": 0.1,
        "x": 136,
        "y": 119,
        "wires": [
            [
                "5e7e8f99.78f0a"
            ]
        ]
    }
]
```
執行結果:<br>
Node-RED收到資料庫回應的成功訊息<br>
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/Node-RED_response_msg.png?raw=true "資料庫回應的成功訊息")

資料庫新增的資料<br>
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/DB_receive_record.png?raw=true "資料庫新增的資料")

## 新增圖形顯示
再傳送三筆溫溼度資料<br>
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/DB_receive_4record.png?raw=true "新增三筆溫溼度資料")

XY折線顯示<br>
![alt text](https://github.com/jackjeanab/Node-RED/blob/master/show_in_UI.png?raw=true "圖形顯示")
