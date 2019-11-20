
## 準備  

### あの画像(domの方)  

### 前回までのマニュアル  

## 復習  
### 変数・if・while  
    <div class="obj">
        【問題】ループと分岐を使って5と６の間にーを表示しよう<br />
        [処理]に条件式を選び表示例のように出力しよう
        <p class="challenge" id="qb10" onClick="dispQ('#qb10','#q10');">問題を表示</p>
        <span class="blind" id="q10">
        <pre class="prettyprint" id="src10">
        var i = 0;
        while(i&lt;10){
            if([処理]){
                console.dir("ー");
            }
            console.dir(i);
            i = i + 1;
        } 
        console.dir("-----END-----");
        </pre>
        <p class="copy" id="copy10">選択</p>
        <div class="select">
        ここから選ぶ<br />
        i&lt;5<br />
        i&lt;6<br />
        i&gt;5<br />
        i&gt;6<br />
        i==5<br />
        i==6<br />
        i!=5<br />
        i!=6<br />
        </div>
        <div class="ans">
        このように表示されれば正解です。<br />
        表示例<br />
        0<br />
        1<br />
        2<br />
        3<br />
        4<br />
        5<br />
        ー<br />
        6<br />
        7<br />
        8<br />
        9<br />
        </div>
        </span>
    </div>
### document.getElementById  
  <div class="obj">
    【問題】id以外を使って画面情報の一部を取得する。<br />
    ①index.htmlとmain.jsに分けて保存する。(現在はhtmlファイルにjsが書かれているので、jsはmain.jsに書くように変更する)<br />
    ②consoleの後ろのコメントに書かれている文字を画面から取得し表示する<br />
    ③コメントを外し、チャレンジ問題に挑戦
    <p class="challenge" id="qb18" onClick="dispQ('#qb18','#q18');">問題を表示</p>
    <span class="blind" id="q18">  
    <pre class="prettyprint" id="src160">
    &lt;html&gt; 
      &lt;body&gt;
        &lt;h1  id="title1"&gt;タイトル1&lt;/h1&gt;
        &lt;h2 class="title2"&gt;タイトル2&lt;/h2&gt;
        &lt;h2 id="title3" &gt;タイトル3&lt;/h2&gt;
        &lt;h2 class="title4" &gt;タイトル3&lt;/h2&gt;
        &lt;h3 &gt;タイトル5&lt;/h3&gt;
        &lt;h4 &gt;タイトル6&lt;/h4&gt;
      &lt;/body&gt;
      &lt;script&gt;
        //getElementByIdでIDを指定して取得
        var title1 = document.getElementById('title1'); 
        console.dir([処理]);//タイトル1をconsoleに表示させる
        //getElementsByClassNameでclassを指定して取得
        var title2 = document.getElementsByClassName('title2'); 
        console.dir(title2[0].innerText);
        //getElementsByIdでidを指定して取得
        [処理]
        console.dir(title3);//タイトル3をconsoleに表示させる
        ///*チャレンジ！getElementsByClassでclassを指定して取得*/
        //[処理]
        //console.dir(title4);//タイトル4
        ///*getElementsByTagNameでタグ名を指定して取得*/
        //var title4 = document.getElementsByTagName('h3'); 
        //console.dir(title5);//タイトル5
        ///*チャレンジ！getElementsByTagNameでタグ名を指定して取得*/
        //[処理]
        //console.dir(title6);//タイトル6       
        &lt;/script&gt; 
    &lt;/html&gt; 
    </pre>
    <p class="copy" id="copy160">選択</p>
    ②はconsoleに<br />
    タイトル1<br />
    タイトル2<br />
    タイトル3<br />
    と表示できれば完成です。
    </span>
  </div>
### innerText  
### クリックイベント  
## 文字の切り抜き  
## 配列  
## localStorage  