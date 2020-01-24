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
function yosoku(key){
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
    mess2.innerText="「"+key+"」から始まる言葉なんか知らん"
}
```


出題される頭文字（key.innerText）をlocalStorageからも探そう!   
画面上(id=mess2)に答えの予想を出す。  


