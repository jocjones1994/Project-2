# Project-2!DOCTYPE html>
<html>
<head> 
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>

<title></title> 
</head>

<body>

<div class="container straighten">
    <div id="popup">
        <div class="marker" id="Future"></div>
       
        <div class="marker" id="MetroBoomin"></div>
        
      
        <img src="http://www.brandnew.hiphop/wp-content/uploads/2015/11/future.jpg"/>
    </div>
</div>

<div class="textbox">
    <div class="popuptitle"> Hip-Hop's Biggest Rapper/Producer Combo?</div>
   Future and Metro Boomin are turning up the streets these days with a bunch of tracks for hip-hop fans. Although Future and Metro worked together before in the past, the duo really blew up after collaborating with Toronto-based rapper Drake on the mixtape What A Time to Be Alive in September 2015. Shortly after, they released Future's album, EVOL in February 2016. EVOL has received rave reviews and has the hip-hop fans asking for more from this new monster duo, which leaves the question-- Is this the best producer/rapper combination in the game right now?
</div>


<style>
.container{
    width: 60%;
    display: inline-block;
    position: relative;
}
.textbox {
    width: 30%;
    display: inline-block;
    vertical-align: top;
    padding: 20px;
    font-family: 'Roboto', sans-serif;
    font-size: 18px;
    line-height: 1.5em;
}
.container img {    
    width: 100%;
}
.marker{
    position: absolute;
    width: 20px;
    height: 20px;
    background-color: yellow;
    border: 2px solid white;
    border-radius: 50%;
    transition: background-color 0.5s ease;
    cursor: pointer;
}
.marker:hover {
    background-color: red;
}
#Future {
    top:50%;
    left: 5%;
}
#MetroBoomin {
    top:30%;
    left: 70%;
}


.straighten:after{
    display:block;
    height:0;
    clear:both;
    visibility:hidden
}

#popup {
    position:relative;
}
.hoverbox {
    position:absolute; 
    padding:0.5em; 
    background:#FFF; 
    box-shadow:1px 1px 8px rgba(0,0,0,.4); 
    z-index:300; 
    font-family:'Roboto', Arial, sans-serif; 
    line-height:1.3em; 
    min-width:100px; 
    max-width:200px;
}
.popuptitle {
    color: #C72428;
    font-family:'Roboto', Arial, sans-serif;
    letter-spacing: 0.01em;
    font-size:18px; 
    font-weight:700;
    clear:both;
}
@media screen and (max-width: 900px) {
.container{
    width: 90%
}
.textbox{
    width: 90%
}
}
</style>

<script>
$(document).ready(function() {

var data = 
[{"id":"Future","name":"Future", "description":"Born Nayvadius DeMun Wilburn, Future is a 32-year-old rapper from Atlanta, Georgia. After releasing his debut album, <i>Pluto</i> in 2012 and his second album, <i>Honest</i> in 2014, Future took his music to a new level with mixtapes<i> Monster</i>, <i>56 Nights</i> and<i> Beast Mode</i>. Then, in 2015, he unexpectedly dropped a third album, <i>Dirty Sprite 2</i>, which practically shot him up to the top of the rap game. <i>DS2</i> went gold and was his first #1 album on the US Billboard 200."},

{"id":"MetroBoomin","name":" Metro Boomin", "description":"Leland T. Wayne A.K.A. Metro Boomin, hails from St.Louis, Missouri. He is a 22-year-old music producer and songwriter. After playing bass guitar in his middle school band, Metro began making beats in seventh grade after receiving a laptop from his mother. He bagan to take trips to Atlanta in 11th grade to collaborate with local artists. After graduating from high school, Metro attended Morehouse College in Atlanta. Since taking a break from school, Metro has worked with famous rappers such as Young Thug, Ludacris, Chief Keef and of course, Future. He has a lot more up his sleeve and the cool part about it is, the guy is only 22!"}];


$(".marker").click(function(){
    $('.textbox').empty();
    for (var i=0; i<data.length; i++) {
    if (this.id == data[i].id) {
        $(".textbox").append('<div class="popuptitle">'+data[i].name+'</div>' + data[i].description);
    } 
    } 
});


var pos, thex, they;

$(".marker").mouseover(function(e){
    $(".hoverbox").remove();

    // POSITIONING THE POP UP
    if (navigator.userAgent.indexOf("Firefox")!=-1){
        
        pos = $("#popup").offset()
        thex = e.pageX - pos.left + 10;
        they = e.pageY - pos.top + 0;
        if (thex > $("#popup").width() - 150) { thex = $("#popup").width() - 150 };
        if (they > $("#popup").height() - 100) { they = $("#popup").height() - 100 };
    } else {

        pos = $("#popup").offset()
        thex = event.pageX - pos.left + 10;
        they = event.pageY - pos.top + 0;
        if (thex > $("#popup").width() - 150) { thex = $("#popup").width() - 150 };
        if (they > $("#popup").height() - 100) { they = $("#popup").height() - 100 };
    }

    // APPENDING TEXT TO THE POP UP
    for (var i=0; i<data.length; i++) {
    if (this.id == data[i].id) {
    $("#popup").append('<div class="hoverbox" style="top:'+they+'px; left:'+thex+'px;"><div class="popuptitle">'+data[i].name+'</div></div>');
    } 
    

    }   
});

$(".marker").mouseleave(function(){
    $(".hoverbox").remove();
});


});//doc ready
</script>

</body>
</html>



