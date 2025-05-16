# 20250516_hakusen

<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>黄帯白線検証</title>
<style>
  body {
    margin: 0;
    padding: 0;
    background: url('https://via.placeholder.com/1200x600/333399/ffffff') no-repeat center center;
    background-size: cover;
    font-family: Arial, sans-serif;
    color: #fff;
  }

  h2 {
    font-size: 3rem;
    margin: 100px;
    line-height: 1.2;
  }

  /* ケース1: 問題が出る一般的なspan */
  .case1 span.yellow {
    background: #ffff00;
    color: #ff0000;
    padding: 0 0.1em;
  }

  /* ケース2: display:inline-block ＋ line-height調整 ＋ box-shadowで白線を消す */
  .case2 span.yellow {
    background: #ffff00;
    color: #ff0000;
    display: inline-block;
    line-height: 1;
    padding: 0.15em 0;
    box-shadow: 0 2px 0 #ffff00;
    -webkit-font-smoothing: antialiased;
    font-smoothing: antialiased;
  }

  /* ケース3: background-clip: text を使う演出 */
  .case3 span.yellow {
    background: linear-gradient(180deg, #ffff00 0%, #ffff00 100%);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    display: inline-block;
  }
    
    
/*背景を表示させる部分*/
body::before {
content:"";
display:block;
position:fixed;
top:0;
left:0;
z-index:-1;
width:100%;
height:100vh;
background:url(https://torokoid.github.io/20250512_tochigi/20250512_013.JPG) center/cover no-repeat;
-webkit-background-size:cover;/*Android4*/
}
    
    
</style>
</head>
<body>

  <h2 class="case1">これは <span class="yellow">黄色帯</span> のテスト1</h2>

  <h2 class="case2">これは <span class="yellow">黄色帯</span> のテスト2（推奨）</h2>

  <h2 class="case3">これは <span class="yellow">黄色帯</span> のテスト3（clip）</h2>

</body>
</html>

