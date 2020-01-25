# 現状の全体を把握しよう
現状がどういう処理をしていたか把握して続きを開始しよう！！  

# localstorageを使ってセーブしよう
```
localStorage.setItem('タイトル',"内容"); //保存
var load = localStorage.getItem('タイトル');　//読み出し
console.log(load); //保存されている単語
```
注意：既に保存されているタイトルで保存すると内容は上書きされます！！！！

# 問題！出た単語を全て保存しよう

wordList(今回の既に出た単語リスト)にpush(追加)する処理と一緒に、  
ブラウザに単語を保存して行こう！    
「りす→すいか→かめら」の順番で入力した場合は
 > ”りす,すいか,かめら”

というカンマ区切りの１つの文字列が保存されているようにしてください。  
＊保存されている内容は、DevツールのApplication->LocalStorageで確認することができます。  


# セーブされている単語を検索しよう

この関数は、引数に指定したひらがなから始まる言葉を探す関数です。  
セーブされている単語の中から先頭のひらがなが合う単語を探します。  
出題が「す」で「すいか」がセーブされている場合  
「すいか」とかどうですか？    
「すいか」がない場合は   
「す」から始まる言葉なんか知らん  
と表示します。  
  
【処理1】【処理2】【処理3】と書いてある場所を正しい処理に変えて、  
これを組み込みシステムが答えを教えてくれるシステムを完成させてください。  
＊答えを教えてくれるのは２問目からで良い。  

```
function yosoku(keyword){
    var storage = localStorage.getItem('タイトル');
    var list = storage.split(',');
    var i = 0;
    var ichimojime;
    while(i<list.length){
        ichimojime = list[i].【処理1】;
        if(ichimojime==【処理2】){
            mess2.innerText="「"+ 【処理3】 +"」とかどうですか？";
            return;
        }
        i=i+1;
    }
    mess2.innerText="「"+keyword+"」から始まる言葉なんか知らん"
}
```


出題される頭文字（key.innerText）をlocalStorageからも探そう!   
画面上(id=mess2)に答えの予想を出す。  




# 対戦相手をCPにする
答えを教えてくれるyosokuに変更を加えて、  
CPと対戦できるように変更しましょう。  
【処理】の部分を変更し、関数を完成させましょう。
```
function cpKaitou(keyword){
    var storage = localStorage.getItem('タイトル');
    var list = storage.split(',');
    var i = 0;
    var ichimojime;
    while(i<list.length){
        ichimojime = list[i].slice(0,1);
        if(ichimojime==keyword){
            mess2.innerText="「"+list[i]+"」";
            【処理】
            return;
        }
        i=i+1;
    }
    mess2.innerText="まいりました。"
}
```


# CP側でも単語チェックをする
①チェックに必要な処理を関数化する。(checkWord)  
②作成した関数に置き換えて、
③cpKaitou内でも使用する。  
④リストとlocalStorageに保存する処理を関数化する(saveWord)  
⑤作成した関数に置き換えて
⑥cpKaitou内でも使用する。  
  


①
```
function checkWord(word){
    console.log("checkWord");
    var flg = 【処理】;
    end = tb.value.slice(-1);//末の文字を取得
    if(end=="ん"){
        flg = 【処理】;
    }else{                
        var i = 0;
        while(i<wordList.length){
            if(【処理】){
                console.dir("すでにでている");                        
                flg = 【処理】;
            }
            i=i+1;
        }
    }
    return flg;
}
```

  
② 文字のチェックを関数に置き換え
```
var flg = checkWord(tb.value);
if(flg==false){
    console.dir("すでにでている");
    alert("すでにでている、もしくは「ん」で終わる単語です");
    return;
}
```
  
  
③　cpKaitou内に組み込む  
  
  
④
```
function saveWord(word){
    console.log("saveWord");
    【処理】
}
```
  

⑤  check関数ないの処理を関数に置き換える
```
//でた言葉を記録する
saveWord(tb.value);
```
  
  
⑥　cpKaitou内に組み込む  