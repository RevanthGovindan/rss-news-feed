var color="";
function topNews(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INtopNews";
    load(url,"Top News");
}
function businessNews(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INbusinessNews";
    load(url,"Business");
}
function southAsia(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INsouthAsiaNews";
    load(url,"South Asia");
}
function worldNews(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INworldNews";
    load(url,"World News");
}
function entertainment(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INentertainmentNews";
    load(url,"Entertainment");
}
function hollywood(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INhollywood";
    load(url,"Hollywood");
}
function sports(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INsportsNews";
    load(url,"Sports");
}
function cricket(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INcricketNews";
    load(url,"Cricket");
}
function f1(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INformulaOne";
    load(url,"F1");
}
function golf(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INgolf";
    load(url,"Golf");
}
function technology(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INtechnologyNews";
    load(url,"Technology");
}
function health(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INhealth";
    load(url,"Health");
}
function lifestyle(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INlifestyle";
    load(url,"Life Style");
}
function oddlyenough(){
    if(color!="")
    {
        document.getElementById(color).style.background="";
        document.getElementById(color).style.color="";
    }
    url="http://feeds.reuters.com/reuters/INoddlyEnoughNews";
    load(url,"Oddly Enough");
}
function load(url,topic){   
    var xhttp = new XMLHttpRequest();
    xhttp.open("GET", url, false);
    xhttp.send();
    var xmlDoc = xhttp.responseXML;
    var data=xmlDoc.getElementsByTagName("item");
    var list="<p class='subtopic'>"+topic+"</p><ul>";
    var title,description,pubdate,link;
    for(var i=0;i<data.length;i++){
        title=data[i].getElementsByTagName("title")[0].childNodes[0].nodeValue;
        description=data[i].getElementsByTagName("description")[0].childNodes[0].nodeValue;
        pubdate=data[i].getElementsByTagName("pubDate")[0].childNodes[0].nodeValue;
        link=data[i].getElementsByTagName("guid")[0].childNodes[0].nodeValue;
        list+="<li><p><a href="+link+">"+title+"</a></p><p>"+description+"</p><p>Posted : "+pubdate+"</p></li>";
    }
    list+="</ul>";
    document.getElementById("demo").innerHTML=list;
    document.getElementById(topic).style.background="#5975D9";
    document.getElementById(topic).style.color="white";
    color=topic;
}