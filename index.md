
<!DOCTYPE html>
<html lang="en">

<head>
    <meta name="description" content="">
    <title>Employee</title>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.14.0/css/all.min.css">
 <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

</head>
<style type="text/css">



.toggle {
	    width: 15%;
    height: 40px;
    position: relative;
    border: solid 6px #04da97;
    border-radius: 55px;
    transition: transform cubic-bezier(0, 0, 0.30, 2) .4s;
    transform-style: preserve-3d;
    perspective: 800px;
}

.toggle>input[type="radio"] {
    display: none;
}

.toggle>#choice1:checked~#flap {
    transform: rotateY(-180deg);
}

.toggle>#choice1:checked~#flap>.content {
    transform: rotateY(-180deg);
}

.toggle>#choice2:checked~#flap {
    transform: rotateY(0deg);
}

.toggle>label {
   display: inline-block;
    min-width: auto;
    padding: 0px;
    font-size: 1em;
    text-align: center;
    color: #04da97;
    cursor: pointer;
    margin: 2px 0px 0px 17px;
}

.toggle>label,
.toggle>#flap {
    font-weight: bold;
    text-transform: capitalize;
}

.toggle>#flap {
    position: absolute;
    top: calc( 0px - 6px);
    left: 50%;
    height: calc(100% + 6px * 2);
    width: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 30px;
    background-color: #04da97;
    border-top-right-radius: 55px;
    border-bottom-right-radius: 55px;
    transform-style: preserve-3d;
    transform-origin: left;
    transition: transform cubic-bezier(0.4, 0, 0.2, 1) .5s;
}

.toggle>#flap>.content {
    color: #333;
    transition: transform 0s linear .25s;
    transform-style: preserve-3d;
}
</style>
<body>

<a href="index.html">home</a>
<a href="about.html">about</a>
<div class="container col-sm-6 my-1 mr-sm-2">
<form name="colorpick" id="colorpick" class="toggle">
    <input type="radio" id="choice1" name="choice" class="colorpick" value="light" checked>
    <label for="choice1"><i class="fas fa-sun"></i></label>
   
    <input type="radio" id="choice2" name="choice" class="colorpick" value="dark">
    <label for="choice2"><i class="far fa-moon"></i></label>
   <div id="flap"><span class="content"></span></div>
</form>
</div>

<div class="container">
<h2>Difference between hook_boot and hook_init Drupal?</h2>

<h4>HOOK_BOOT</h4>
<ul>
  <li>Even cached page executes this hook</li>
  <li>This hook is called before modules or most include files are loaded into memory.</li>
 <li> It happens while Drupal is still in bootstrap mode.</li>
  </ul>
 <h4> HOOK_INIT :</h4>

 <li> Perform setup tasks for non-cached page requests.</li>
  <li>Cached page doesn???t run this hook.</li>
  <li>When this hook is called, all modules are already loaded in memory.</li>
  <li>It happens after bootstrap mode.</li></ul>

  </div>


 <script
            src="https://code.jquery.com/jquery-3.3.1.min.js"
            integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
            crossorigin="anonymous"
        ></script>
        <script
            src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
            integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
            crossorigin="anonymous"
        ></script>
        <script src="js/styleSwitcher.js"></script>
<script type="text/javascript">
	$(document).ready(function(){
    $('#colorpick').styleSwitcher();
})
</script>
<script type="text/javascript">
	const st = {};

st.flap = document.querySelector('#flap');
st.toggle = document.querySelector('.toggle');

st.choice1 = document.querySelector('#choice1');
st.choice2 = document.querySelector('#choice2');

st.flap.addEventListener('transitionend', () => {

    if (st.choice1.checked) {
        st.toggle.style.transform = 'rotateY(-15deg)';
        setTimeout(() => st.toggle.style.transform = '', 400);
    } else {
        st.toggle.style.transform = 'rotateY(15deg)';
        setTimeout(() => st.toggle.style.transform = '', 400);
    }

})

st.clickHandler = (e) => {

    if (e.target.tagName === 'LABEL') {
        setTimeout(() => {
            st.flap.children[0].textContent = e.target.textContent;
        }, 250);
    }
}

document.addEventListener('DOMContentLoaded', () => {
    st.flap.children[0].textContent = st.choice2.nextElementSibling.textContent;
});

document.addEventListener('click', (e) => st.clickHandler(e));
</script>
  


</body>
</html>
