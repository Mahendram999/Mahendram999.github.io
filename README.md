[Mahendra M Digital Projects.html](https://github.com/user-attachments/files/33876579/Mahendra.M.Digital.Projects.html)
<head>
    
<style>
    body{
        text-align: center;
        font-size: 20px;
        color: blue;
        background: red;
        }body{
            text-align:center;
            font-size: 20px;
            color: red;
            background: Orange;
        }
            
 
    
    
        .embed-box {
          margin: 75px 0px 75px 0px;
        }
         
        </style>

</head>



<body>
<h1>My Digital Projects, by Mahendra M</h1>



<div class=embed-box>
    <h2>My 1st Project:Infographic about a Place</h2>
    <iframe
      src="https://express.adobe.com/embedLink/urn:aaid:sc:VA6C2:3487be30-d8a9-547d-b6ee-17f0a964a939?promoid=Y69SGM5H&sdid=C4SZ2FYJ&mv=other"
      width="1280"
      height="720"
      loading="lazy"
      allowfullscreen="allowfullscreen"
      allow="clipboard-write; fullscreen"
      referrerpolicy="strict-origin-when-cross-origin"
      frameborder="0"
      style="width:80%; max-width:1280px; height:auto; aspect-ratio:1280/720; border:0; display:block; margin:0 auto;"

    ></iframe> 
    
</div>
<button class="likeButtons">Like</button>
<span class="numLikes">0</span>






<div class="embed-box">
    <h2>My 2nd Project: Video About My Day</h2>
    <iframe
  src="https://express.adobe.com/embedLink/urn:aaid:sc:VA6C2:20f42dcd-03e1-5dcf-af3b-94f7dd04cbac?promoid=Y69SGM5H&sdid=C4SZ2FYJ&mv=other"
  width="1280"
  height="720"
  loading="lazy"
  allowfullscreen="allowfullscreen"
  allow="clipboard-write; fullscreen"
  referrerpolicy="strict-origin-when-cross-origin"
  frameborder="0"
  style="width:80%; max-width:1280px; height:auto; aspect-ratio:1280/720; border:0; display:block; margin:0 auto;"

></iframe>
      
    
    </iframe>
    
    
    <button class="likeButtons">Like</button>
    <span class="numLikes">0</span>
    
</div>


    
    
    <script type="module">


      
      // Import the functions you need from the SDKs you need
        import { initializeApp } from "https://www.gstatic.com/firebasejs/13.1.0/firebase-app.js";
        import { getDatabase, ref, set, onValue } from "https://www.gstatic.com/firebasejs/13.1.0/firebase-database.js";
        // TODO: Add SDKs for Firebase products that you want to use
        // https://firebase.google.com/docs/web/setup#available-libraries

        // Your web app's Firebase configuration
        const firebaseConfig = {
          apiKey: "AIzaSyAQ7wFg7rIh6LYvno-OLela-y-CiLu3QZk",
          authDomain: "likebuttons1-d337d.firebaseapp.com",
          projectId: "likebuttons1-d337d",
          storageBucket: "likebuttons1-d337d.firebasestorage.app",
          messagingSenderId: "953839244975",
          appId: "1:953839244975:web:2f139471db1d97ca4f265a"
        };

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const db = getDatabase(app);
    	const likeButtons = document.querySelectorAll(".likeButtons")
    	const numLikes = document.querySelectorAll(".numLikes")

    	for (let i=0; i<likeButtons.length; i++) {
    		likeButtons[i].addEventListener('click', function(){ Like(i) })
            onValue(ref(db, "/project "+i+"/numLikes"), (snapshot) => {
            			let data = snapshot.val();
            			numLikes[i].innerHTML = data
            		});
            
    	}

    	function Like(i) {
    		let numberLikes = parseInt(numLikes[i].innerHTML)
    		numberLikes = numberLikes + 1
    		set(ref(db, "project " + i), {
    			numLikes: numberLikes,
    		});
    		
    	}
    </script>
    
</body>
