## 画面つくる
```
<html>
    <body style="text-align: center;">  
        <p id='char'>ひらがなを入力してください</p>  
        <input id='tt' value=''>  
        <button id='bt'>送信</button>  
        <button id='reset'>リセット</button>  
        <script>  
            var startText = "り";//開始の文字  
            var out = document.getElementById("char");  
            var t = document.getElementById("tt");    
        </script>  
    </body>  
</html>
```



## データ入出力
テキストを入力しボタンを押すとPタグに表示されるようにする。  
```
var bt = document.getElementById("bt");
bt.addEventListener('click',function(){
    var word = [処理];//テキストボックスの値取得    
    out.innerText = [処理];  //Pタグに値を出力
})
```

## データチェック
•Pタグに表示されている最後の文字が、入力された先頭文字(startText)であることを確認する  
•入力された文字の末端が「ん」ではないことを確認する  
word.slice(0,1);   
word.slice(-1);
```
var bt = document.getElementById("bt");
bt.addEventListener('click',function(){
　var word = [処理]
　//入力文字のチェック
  var flg = checkWord(word,startText);

  //値の出力
  out.innerText = [処理];  //Pタグに値を出力
});

function checkWord(word,startText){
    [処理(startTextから始まり、「ん」で終わらないことの確認)]
}
```

## データ保存機能について
localstrageの説明  
```
localStorage.setItem(key,value);

localStorage.getItem(key);
```

## データ保存機能を作成する
入力したものをlocalStorageに保存していく    
*saveに保存してたものを取得し「,」＋「新単語」で保存し直す
```
    function saveWord(word){
            var save = [処理]
            localStorage.setItem('game',save+","+word);
    }

```






## データ読み出し
localStrageの値を配列に変換してkeyArrayに代入する。
```
    function loadWord(word,endChar){
        var keyArray = [処理]
        var out_key = "";
        var i = 0;
        while(i < keyArray.length){
            console.log(keyArray [i]);
            if(keyArray [i].slice(0,1) == endChar){
                out_key = keyArray [i];
                break;
            }
        }
        return out_key;
    }
```




## データクリア
```
    document.getElementById('reset')
    .addEventListener('click',function (){
        localStorage.clear();
    });
```

## データ多重保存禁止(チャレンジ)
データ保存時にすでに保存されている場合は保存しないように設定する




## 先頭null禁止(チャレンジ)
データ保存時の「,」＋「新単語」を最初はやらない



## 初期設定(チャレンジ)
最初からある程度単語をしている状態にしよう

   
   
   


------


## アンケート
https://forms.gle/AeR1Q7vSuZBs2C6H9
