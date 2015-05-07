# AppProgram-TuFuturo
Aplicación para tomar asistencia en Programá tu futuro

<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>Programá tu futuro app</title>
        
        <style type="text/css">

            /*-------------------------
    Simple reset
--------------------------*/


*{
    margin:0;
    padding:0;
}


/*-------------------------
    General Styles
--------------------------*/


html{
    background:url('bg_tile.jpg') #161718;
}

body{
    background:url('bg_center.jpg') no-repeat center center;
    min-height: 600px;
    padding: 100px 0 0;
    font:14px/1.3 'Segoe UI',Arial, sans-serif;
}

a, a:visited {
    text-decoration:none;
    outline:none;
    color:#54a6de;
}

a:hover{
    text-decoration:underline;
}

section, footer{
    display: block;
}


/*----------------------------
    Styling the forms
-----------------------------*/


#formContainer{
    width:288px;
    height:321px;
    margin:0 auto;
    position:relative;
    z-index:1;
    
    -moz-perspective: 800px;
    -webkit-perspective: 800px;
    perspective: 800px;
}

#formContainer form{
    width:100%;
    height:100%;
    position:absolute;
    top:0;
    left:0;
    
    /* Enabling 3d space for the transforms */
    -moz-transform-style: preserve-3d;
    -webkit-transform-style: preserve-3d;
    transform-style: preserve-3d;
    
    /* When the forms are flipped, they will be hidden */
    -moz-backface-visibility: hidden;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
    
    /* Enabling a smooth animated transition */
    -moz-transition:0.8s;
    -webkit-transition:0.8s;
    transition:0.8s;
    
    /* Configure a keyframe animation for Firefox */
    -moz-animation: pulse 2s infinite;
    
    /* Configure it for Chrome and Safari */
    -webkit-animation: pulse 2s infinite;
}


/* Firefox Keyframe Animation */
@-moz-keyframes pulse{
    0%{     box-shadow:0 0 1px #008aff;}
    50%{    box-shadow:0 0 8px #008aff;}
    100%{   box-shadow:0 0 1px #008aff;}
}

/* Webkit keyframe animation */
@-webkit-keyframes pulse{
    0%{     box-shadow:0 0 1px #008aff;}
    50%{    box-shadow:0 0 10px #008aff;}
    100%{   box-shadow:0 0 1px #008aff;}
}

#login{
    background:url('login_form_bg.jpg') no-repeat;
    z-index:100;
}

#recover{
    background:url('recover_form_bg.jpg') no-repeat;
    z-index:1;
    opacity:0;
    
    /* Rotating the recover password form by default */
    -moz-transform:rotateY(180deg);
    -webkit-transform:rotateY(180deg);
    transform:rotateY(180deg);
}

#formContainer.flipped #login{
    
    opacity:0;
    
    /**
     * Rotating the login form when the
     * flipped class is added to the container
     */
    
    -moz-transform:rotateY(-180deg);
    -webkit-transform:rotateY(-180deg);
    transform:rotateY(-180deg);
}

#formContainer.flipped #recover{
    
    opacity:1;
    
    /* Rotating the recover div into view */
    -moz-transform:rotateY(0deg);
    -webkit-transform:rotateY(0deg);
    transform:rotateY(0deg);
}


/*----------------------------
    Inputs, Buttons & Links
-----------------------------*/


#login .flipLink,
#recover .flipLink{
    
    /* The blue ribbon links */
    
    height: 65px;
    overflow: hidden;
    position: absolute;
    right: 0;
    text-indent: -9999px;
    top: 0;
    width: 65px;
}

#recover .flipLink{
    right:auto;
    left:0;
}

#login:after{
    /* The "Click here" tooltip */
    width:98px;
    height:16px;
    content:'';
    background:url('click_here.png') no-repeat;
    position:absolute;
    right:-120px;
    top:22px;
}

input[type=text],input[type=password]{
    /* The text fields */
    font: 15px 'Segoe UI',Arial,sans-serif;
    border: none;
    background:none;
    height: 36px;
    left: 26px;
    position: absolute;
    top: 176px;
    width: 234px;
    text-indent: 8px;
    text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.3);
    color:#eee;
    outline:none;
}

#loginPass{
    top: 215px;
}

#recoverEmail{
    top:215px;
}

input[type=submit]{
    
    /* Submit button */
    
    opacity:0.9;
    position:absolute;
    top:262px;
    left:25px;
    width: 239px;
    height:36px;
    cursor:pointer;
    border-radius:6px;
    box-shadow:0 1px 1px #888;
    border:none;
    color:#fff;
    font:14px/36px 'Segoe UI Light','Segoe UI',Arial,sans-serif;
    
    /* CSS3 Gradients */
    
    background-image: linear-gradient(bottom, rgb(80,102,127) 50%, rgb(87,109,136) 50%, rgb(106,129,155) 100%);
    background-image: -o-linear-gradient(bottom, rgb(80,102,127) 50%, rgb(87,109,136) 50%, rgb(106,129,155) 100%);
    background-image: -moz-linear-gradient(bottom, rgb(80,102,127) 50%, rgb(87,109,136) 50%, rgb(106,129,155) 100%);
    background-image: -webkit-linear-gradient(bottom, rgb(80,102,127) 50%, rgb(87,109,136) 50%, rgb(106,129,155) 100%);
    background-image: -ms-linear-gradient(bottom, rgb(80,102,127) 50%, rgb(87,109,136) 50%, rgb(106,129,155) 100%);
    
    background-image: -webkit-gradient(
        linear,
        left bottom,
        left top,
        color-stop(0.5, rgb(80,102,127)),
        color-stop(0.5, rgb(87,109,136)),
        color-stop(1, rgb(106,129,155))
    );
}

input[type=submit]:hover{
    opacity:1;
}

input::-webkit-input-placeholder {
    color:#eee;
}


/*----------------------------
    The Footer
-----------------------------*/


footer{
    background-color: #111111;
    bottom: 0;
    box-shadow: 0 -1px 2px #111111;
    height: 45px;
    left: 0;
    position: fixed;
    width: 100%;
    z-index: 100000;
}

footer h2{
    color: #EEEEEE;
    font-size: 14px;
    font-weight: normal;
    left: 50%;
    margin-left: -400px;
    padding: 13px 0 0;
    position: absolute;
    width: 540px;
}

footer h2 i{
    font-style:normal;
    color:#888;
}

footer a.tzine,a.tzine:visited{
    color: #999999;
    font-size: 12px;
    left: 50%;
    margin: 16px 0 0 110px;
    position: absolute;
    text-decoration: none;
    top: 0;
}

footer a i{
    color:#ccc;
    font-style: normal;
}

footer a i b{
    color:#c92020;
    font-weight: normal;
}


        </style>
    </head>
    
    <body>

		<div id="formContainer">
			<form id="login" method="post" action="./">
				<a href="#" id="flipToRecover" class="flipLink">Forgot?</a>
				<input type="text" name="loginEmail" id="loginEmail" placeholder="Email" />
				<input type="password" name="loginPass" id="loginPass" placeholder="Password" />
				<input type="submit" name="submit" value="Login" />
			</form>
			<form id="recover" method="post" action="./">
				<a href="#" id="flipToLogin" class="flipLink">Forgot?</a>
				<input type="text" name="recoverEmail" id="recoverEmail" placeholder="Your Email" />
				<input type="submit" name="submit" value="Recover" />
			</form>
		</div>

        <footer>
	        <h2><i>User Interface:</i> 1. Pantalla de logueo</h2>
            <a class="tzine" href="http://www.buenosaires.gob.ar/educacion/programatufuturo">Visiten la página <i><b>Programá tu futuro</b></i> para encontrar el sentido de la vida.</a>
        </footer>
        
        <!-- JavaScript includes -->
		<script src="http://code.jquery.com/jquery-1.7.1.min.js"></script>
	    <script type="text/javascript">

            $(function(){
                
                // Checking for CSS 3D transformation support
                $.support.css3d = supportsCSS3D();
                
                var formContainer = $('#formContainer');
                
                // Listening for clicks on the ribbon links
                $('.flipLink').click(function(e){
                    
                    // Flipping the forms
                    formContainer.toggleClass('flipped');
                    
                    // If there is no CSS3 3D support, simply
                    // hide the login form (exposing the recover one)
                    if(!$.support.css3d){
                        $('#login').toggle();
                    }
                    e.preventDefault();
                });
                
                formContainer.find('form').submit(function(e){
                    // Preventing form submissions. If you implement
                    // a backend, you might want to remove this code
                    e.preventDefault();
                });
                
                
                // A helper function that checks for the 
                // support of the 3D CSS3 transformations.
                function supportsCSS3D() {
                    var props = [
                        'perspectiveProperty', 'WebkitPerspective', 'MozPerspective'
                    ], testDom = document.createElement('a');
                      
                    for(var i=0; i<props.length; i++){
                        if(props[i] in testDom.style){
                            return true;
                        }
                    }
                    
                    return false;
                }
            });


        </script>
    
    </body>
</html>
