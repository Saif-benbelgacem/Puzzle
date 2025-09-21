<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>QRPuzzle</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 24px; max-width: 700px; margin:auto; line-height:1.6; }
    .card { border:1px solid #ddd; padding:18px; border-radius:8px; box-shadow: 0 2px 6px rgba(0,0,0,0.06); }
    input { padding:8px; font-size:16px; margin-top:12px; width:150px; }
    button { padding:8px 12px; font-size:16px; margin-left:8px; margin-top:12px; }
    .ok { color: green; font-weight: bold; }
    .bad { color: red; font-weight: bold; }
  </style>
</head>
<body>
  <div class="card">
    <h2>Puzzle</h2>
    <p>Read carefully:</p>
    <p>
      awhispering winds move softly,  
      beacons glow beyond the hills,  
      alight the tiny path of flame,  
      again, the journey goes on bright,  
      bunderneath the quiet shadow waits,  
      aloud the voices call gently,  
      beaming stars guide the way,  
      alight the path with hope and light,  
      alight the final spark ignites the night a is one, b is zero
      <br>
    </p>
    <p>Enter the code:</p>
    <input id="answer" maxlength="9" autofocus placeholder="" />
    <button onclick="check()">Check</button>
    <p id="msg"></p>
  </div>
  <script>
    function check(){
      const a = document.getElementById('answer').value.trim();
      const msg = document.getElementById('msg');
      const correctCode = '101101101'; // sequence from poem
      if(!a){ 
        msg.textContent = 'Please enter the binary code.'; 
        msg.className='bad'; 
        return; 
      }
      if(a === correctCode){
        // LINK to the new hard mobile maze
        msg.innerHTML = '✅ Correct! <a href="maze.html">Click here for your next clue</a>';
        msg.className='ok';
      } else {
        msg.textContent = '❌ Wrong, try again.';
        msg.className='bad';
      }
    }
  </script>
</body>
</html>
