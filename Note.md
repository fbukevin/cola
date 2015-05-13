

使用 cola 碰到的一些問題
1. 安裝
Python set up package path 的另一方法
在site-packages下新建一?cola.pth文件，里面?上路?：/to/path/cola (root of cola folder)。
Python 的 package 在 Windows 中是放在 site-packages
在 Linux 中是放在 dist-packages
這兩個資料夾在安裝 python 時都會存在，所以忘記了就要兩個都try看
設定完後就可以直接用 python2 REPL 來 import 看看了

2. pip 安裝 pyyaml 一直有 Unicode 編碼問題
改用 sudo python2 -m easy_install pyyaml 就好了

3. 注意！要用 python2，cola 還不支援 python3

4. dependency 缺少 rsa, mongoengine 套件的問題，pip 仍不能裝，改用 sudo python2 -m easy_install rsa
	缺少 mechanize，可用 pip2 安裝

5. mongoengine.connection.ConnectionError: Cannot connect to database default
sudo pip2 install pymongo==2.8

6. No JSON object could be decoded
	username 應該是 fbukevin@gmail.com 而非 VeckHsiao

7. 好像只有第一次啟動時會抓到 weibo.yaml 中設定的 start uid
   中斷後再啟動就都不會了
   不曉得怎麼指定只抓某個帳號和數量

***
master 上要用另一台電腦去 python stop.py 才能終止，不可用 Ctrl+C
develop 上要直接用 ctrl + C
資料直接存進 Weibo

$ mongo sina   # name 可在 weibo.yaml 中改
>>> show collections
>>> db.micro_blog.find()

用了 mongo-express!!!!
就跟 phpmyadmin 一樣好用啊!!! (甚至比較好看XD)
不過還不是很完整
要重新啟動才會看到資料庫的刪增

還有一個有在動的 develop 分支

