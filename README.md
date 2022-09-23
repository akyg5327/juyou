#########自身で作成するファイルリスト########################################################

#どこに何のファイルを作成したのか参考にしてください
/juyou/python/Dockefile     
/juyou/python/requirements.tx   #pythonにインストールする必要なパッケージ名のリストファイル
/juyou/mysqlite/Dockerfile      
/juyou/docker-compose.yml       #２つのコンテナを連結するためのyamlファイル





##########下準備の手順########################################################################

#任意の名前のworkspace作成、今回は/juyouとしてある
$ mkdir (workspace-name)


#workspaceと同じ階層にディレクトリpythonとmysqliteを作成
$ mkdir python mysqlite


#作成したディレクトリ内に以下のようなファイルを作成（ファイルの作り方はなんでもOK）
$ vi python/Dockerfile
$ vi python/requirements.txt
$ vi mysqlite/Dockerfile

#workspace内で以下のファイル作成
$ vi docker-compose.yml





##########コンテナ起動の手順##################################################################

#以下自分のworkspace内で実行していく
$ cd
$ cd (worlspace-name)

#最初に実行するコマンド
docker-compose run python-django-opencv  django-admin.py startproject composeexample .

#コンテナ二つを起動するコマンド
docker-compose up -d

#起動されたコンテナの確認
docker-compose ps                       

#ファイル所有権の変更
sudo chown -R $USER:$USER .

#Django の Welcome ページを確認
http://localhost:8000



###以下はメモ###
#１つずつコンテナ起動
docker-compose run db-sqlite3
docker-compose run python-django-opencv
