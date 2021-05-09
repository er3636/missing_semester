# Lecture-2

- 括弧の中でコマンドを扱うことで、そのコマンドの実行結果を入力・出力にすることができる。
``` 
cat <(pwd)
# /home/er3636

echo $(pwd)
# /home/er3636
```

- エラー処理や例外処理の例：
```
false || echo "Oops fail"
# 最初の部分はfalseの場合echoが実行される。trueの場合実行されない。
```
