---
tags: []
---
* toc
{:toc}

> [Bookmarklet Maker](https://caiorss.github.io/bookmarklet-maker/)

### Twitter Ads

```js
// Pools (all)
var spans = [...document.querySelectorAll("span")]
var h2s = [...document.querySelectorAll("h2")]

// Who to follow
var who = spans.filter(a => a.textContent.includes("Who to follow"))
who.forEach((a) => {
  var sign = a.closest('[data-testid="cellInnerDiv"]');
  var t1 = sign.nextSibling;
  var t2 = t1.nextSibling;
  var t3 = t2.nextSibling;
  if (sign) sign.style.display = 'none';
  if (t1) t1.style.display = 'none';
  if (t2) t2.style.display = 'none';
  if (t3) t3.style.display = 'none';
})

// Ad
var ads = spans.filter(a => a.textContent.includes("Ad"))
ads.forEach(a => console.log(a.closest('article').style.display = 'none'))

// Lists
var lists = spans.filter(a => a.textContent.includes('Discover new Lists'))
lists.forEach((a) => {
  var disc = a.closest('[data-testid="cellInnerDiv"]')
  var t1 = disc.nextSibling
  var t2 = t1.nextSibling
  var t3 = t2.nextSibling
  if (disc) disc.style.display = 'none';
  if (t1) t1.style.display = 'none';
  if (t2) t2.style.display = 'none';
  if (t3) t3.style.display = 'none';
})

// People
var peo = h2s.filter(a => a.textContent.includes('People'))
peo.forEach((a) => {
  var disc = a.closest('[data-testid="cellInnerDiv"]')
  var t1 = disc.nextSibling
  var t2 = t1.nextSibling
  var t3 = t2.nextSibling
  if (disc) disc.style.display = 'none';
  if (t1) t1.style.display = 'none';
  if (t2) t2.style.display = 'none';
  if (t3) t3.style.display = 'none';
})

// Creators
var creo = h2s.filter(a => a.textContent.includes('Creators for you'))
creo.forEach((a) => {
  var disc = a.closest('[data-testid="cellInnerDiv"]')
  var t1 = disc.nextSibling
  var t2 = t1.nextSibling
  var t3 = t2.nextSibling
  if (disc) disc.style.display = 'none';
  if (t1) t1.style.display = 'none';
  if (t2) t2.style.display = 'none';
  if (t3) t3.style.display = 'none';
})

// Show
var show = spans.filter(a => a.textContent.includes("Show more"))
show.forEach((a) => {
  console.log(a.closest('[data-testid="cellInnerDiv"]').style.display = 'none')
})

// View all
var view = spans.filter(a => a.textContent.includes("View all"))
view.forEach((a) => {
  console.log(a.closest('[data-testid="cellInnerDiv"]').style.display = 'none')
})

// Discover
var disc = spans.filter(a => a.textContent.includes("Discover more"))
disc.forEach((a) => {
  var lui = a.closest('[data-testid="cellInnerDiv"]')
  var next = lui.nextSibling
  if (lui) lui.remove();
  if (next) next.style.display = 'none';
})
```

### PRI New Page New Tab

```js
javascript:var w=window.open();
var dat=new Date().toLocaleDateString('en-CA');
var time=new Date().toISOString().substring(11, 19);
var title=encodeURIComponent(document.title);
var offset=-(new Date().getTimezoneOffset()/60);
var host=location.host.replace("https://","").replace("http://","").replace("www.","");
var category=host.substring(0, host.lastIndexOf("."));
var cat = category || "uncategorized"
var sign=(offset > 0) ? "%2B" + offset : "-" + offset;
var image=(document.querySelector("meta[property='og:image']"))?"%0Aimage:%20"+document.querySelector("meta[property='og:image']").getAttribute('content'):"";
var slug=document.title.toString().toLowerCase().trim().replace(/[^\w\s-]/g,'').replace(/[\s_-]+/g,'_').replace(/^-+|-+$/g,'');
try{
  s=document.selection.createRange().text
}catch(_){
  s=document.getSelection()
};
w.location="https://github.com/trasparente/pri/new/main?filename="+cat+"/_posts/"+dat+"-"+slug+".md&value=---%0Atitle:%20"+title+"%0Asource_url:%20"+location+"%0Adate:%20"+dat+"%20"+time+"%20"+sign+image+"%0Atags:%20%0A---%0A%0A%23%20"+title+"%0A%0A-%20"+encodeURIComponent(s);w.document.close();
```

```js
javascript:(function()%7Bjavascript%3Avar%20w%3Dwindow.open()%3B%0Avar%20dat%3Dnew%20Date().toLocaleDateString('en-CA')%3B%0Avar%20time%3Dnew%20Date().toISOString().substring(11%2C%2019)%3B%0Avar%20title%3DencodeURIComponent(document.title)%3B%0Avar%20offset%3D-(new%20Date().getTimezoneOffset()%2F60)%3B%0Avar%20host%3Dlocation.host.replace(%22https%3A%2F%2F%22%2C%22%22).replace(%22http%3A%2F%2F%22%2C%22%22).replace(%22www.%22%2C%22%22)%3B%0Avar%20category%3Dhost.substring(0%2C%20host.lastIndexOf(%22.%22))%3B%0Avar%20cat%20%3D%20category%20%7C%7C%20%22uncategorized%22%0Avar%20sign%3D(offset%20%3E%200)%20%3F%20%22%252B%22%20%2B%20offset%20%3A%20%22-%22%20%2B%20offset%3B%0Avar%20image%3D(document.querySelector(%22meta%5Bproperty%3D'og%3Aimage'%5D%22))%3F%22%250Aimage%3A%2520%22%2Bdocument.querySelector(%22meta%5Bproperty%3D'og%3Aimage'%5D%22).getAttribute('content')%3A%22%22%3B%0Avar%20slug%3Ddocument.title.toString().toLowerCase().trim().replace(%2F%5B%5E%5Cw%5Cs-%5D%2Fg%2C'').replace(%2F%5B%5Cs_-%5D%2B%2Fg%2C'_').replace(%2F%5E-%2B%7C-%2B%24%2Fg%2C'')%3B%0Atry%7B%0A%20%20s%3Ddocument.selection.createRange().text%0A%7Dcatch(_)%7B%0A%20%20s%3Ddocument.getSelection()%0A%7D%3B%0Aw.location%3D%22https%3A%2F%2Fgithub.com%2Ftrasparente%2Fpri%2Fnew%2Fmain%3Ffilename%3D%22%2Bcat%2B%22%2F_posts%2F%22%2Bdat%2B%22-%22%2Bslug%2B%22.md%26value%3D---%250Atitle%3A%2520%22%2Btitle%2B%22%250Asource_url%3A%2520%22%2Blocation%2B%22%250Adate%3A%2520%22%2Bdat%2B%22%2520%22%2Btime%2B%22%2520%22%2Bsign%2Bimage%2B%22%250Atags%3A%2520%250A---%250A%250A%2523%2520%22%2Btitle%2B%22%250A%250A-%2520%22%2BencodeURIComponent(s)%3Bw.document.close()%3B%7D)()%3B
```

### PRI Issue Selection New Tab

```js
javascript:var w=window.open();try{s=document.selection.createRange().text}catch(_){s=document.getSelection()};w.location="https://github.com/trasparente/pri/issues/new?title="+encodeURIComponent(document.title)+"&body="+location+String.fromCharCode(37)+"0A---"+String.fromCharCode(37)+"0A"+encodeURIComponent(s);w.document.close();
```

### YouTube First Frame
`https://www.youtube.com/watch?v=...` to `https://i.ytimg.com/vi/.../maxresdefault.jpg`
```js
javascript:(function(s){ s=location.href.match(/v=([^&#]{5,})/)[1];location="https://i.ytimg.com/vi/"+s+"/maxresdefault.jpg";})()
```

### NYTimes break
```js
javascript:document.getElementById("gateway-content").remove();app=document.querySelector('#app>div>div');app.style.overflow='auto';document.querySelector('#app>div>div>div:last-child').remove()
```

### inaltoiquori Open .fb-post
```js
javascript:void(window.location.href=document.getElementsByClassName('fb-post')[0].getAttribute('data-href'))
```

### Instagram big image
```js
javascript:(function(){;!function(e)%7Bvar%20t=%7B%7D;function%20n(a)%7Bif(t%5Ba%5D)return%20t%5Ba%5D.exports;var%20r=t%5Ba%5D=%7Bi:a,l:!1,exports:%7B%7D%7D;return%20e%5Ba%5D.call(r.exports,r,r.exports,n),r.l=!0,r.exports%7Dn.m=e,n.c=t,n.d=function(e,t,a)%7Bn.o(e,t)%7C%7CObject.defineProperty(e,t,%7Benumerable:!0,get:a%7D)%7D,n.r=function(e)%7B%22undefined%22!=typeof%20Symbol&&Symbol.toStringTag&&Object.defineProperty(e,Symbol.toStringTag,%7Bvalue:%22Module%22%7D),Object.defineProperty(e,%22__esModule%22,%7Bvalue:!0%7D)%7D,n.t=function(e,t)%7Bif(1&t&&(e=n(e)),8&t)return%20e;if(4&t&&%22object%22==typeof%20e&&e&&e.__esModule)return%20e;var%20a=Object.create(null);if(n.r(a),Object.defineProperty(a,%22default%22,%7Benumerable:!0,value:e%7D),2&t&&%22string%22!=typeof%20e)for(var%20r%20in%20e)n.d(a,r,function(t)%7Breturn%20e%5Bt%5D%7D.bind(null,r));return%20a%7D,n.n=function(e)%7Bvar%20t=e&&e.__esModule?function()%7Breturn%20e.default%7D:function()%7Breturn%20e%7D;return%20n.d(t,%22a%22,t),t%7D,n.o=function(e,t)%7Breturn%20Object.prototype.hasOwnProperty.call(e,t)%7D,n.p=%22%22,n(n.s=3)%7D(%5Bfunction(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e,t)%7Bt=t%7C%7Cwindow%7C%7Cdocument.documentElement;var%20n=e.getBoundingClientRect();return%20n.bottom%3E0&&n.right%3E0&&n.left%3C(t.innerWidth%7C%7Ct.clientWidth)&&n.top%3C(t.innerHeight%7C%7Ct.clientHeight)%7D%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=%5B%5D;t.push(e);for(;e.parentNode;)t.unshift(e.parentNode),e=e.parentNode;return%20t%7D%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e,t,n)%7Bfor(var%20a=0;a%3Ce.length;a++)t.call(n,a,e%5Ba%5D)%7D%7D,function(e,t,n)%7B%22use%20strict%22;var%20a=f(n(4)),r=f(n(2)),o=f(n(0)),i=f(n(6)),s=f(n(7)),l=f(n(8)),d=f(n(9)),u=f(n(10)),c=f(n(11)),g=f(n(14)),m=f(n(15));function%20f(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7Dvar%20h=%7BVERSION:%224.0.0%22,hostname:window.location.hostname,path:window.location.pathname,images:%5B%5D,imagesOnViewPort:%5B%5D,videos:document.querySelectorAll(%22video%22),regexOriginalImage:/%5C/%5Ba-z%5D+%5Cd+%5Ba-z%5D?x%5Cd+%5Ba-z%5D?/,regexMaxResImage:/%5C/%5Ba-z%5D+%5B1080%5D+%5Ba-z%5D?x%5B1080%5D+%5Ba-z%5D?/,regexPath:/%5E%5C/p%5C//,regexHostname:/instagram%5C.com/,regexStoriesURI:/stories%5C/(.*)+/,regexURL:/(%5B--:%5Cw?@%25&+~#=%5D*%5C.%5Ba-z%5D%7B2,4%7D%5C/%7B0,2%7D)((?:%5B?&%5D(?:%5Cw+)=(?:%5Cw+))+%7C%5B--:%5Cw?@%25&+~#=%5D+)?/,foundByModule:null,probablyHasAGallery:%7Bcheck:null,byModule:%22%22%7D,setImageLink:function(e)%7Bthis.imageLinkBeforeParse=e,this.regexMaxResImage.test(e)?this.imageLink=e:this.imageLink=this.regexOriginalImage.test(e)?e.replace(this.regexOriginalImage,%22%22):e%7D,foundVideo:!1,foundImage:!1,imageLink:!1,imageLinkBeforeParse:!1,alertNotInInstagramPost:!1,context:%7BhasMsg:!1,msg:%22%22%7D%7D,p=document.images;(0,r.default)(p,function(e,t)%7B((0,i.default)(t)%7C%7C2===p.length)&&(h.images.push(t),(0,o.default)(t)&&h.imagesOnViewPort.push(t))%7D),h.regexHostname.test(h.hostname)%7C%7Cwindow.alert((0,a.default)(%22index@alert_onlyWorks%22)),h.regexHostname.test(h.hostname)&&(!1===(0,s.default)(h)&&!1===(0,l.default)(h)&&!1===(0,d.default)(h)&&!1===(0,u.default)(h)&&!1===(0,c.default)(h)&&!1===(0,g.default)(h)&&!1===(0,m.default)(h)&&(h.context.hasMsg=!1),h.context.hasMsg&&window.alert((0,a.default)(h.context.msg)),!h.alertNotInInstagramPost%7C%7Ch.foundVideo%7C%7Ch.foundImage%7C%7Cwindow.alert((0,a.default)(%22index#program@alert_dontFound%22)))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D);var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(5));var%20r=%7Bde:%22de-DE%22,pt:%22pt-BR%22,en:%22en-US%22,%22en-GB%22:%22en-US%22%7D%5Bnavigator.language%5D;function%20o(e)%7Bvar%20t=arguments.length%3E1&&void%200!==arguments%5B1%5D?arguments%5B1%5D:r;try%7Bif(a.default.langs.hasOwnProperty(t)%7C%7C(t=%22en-US%22),a.default.langs%5Bt%5D%5Be%5D)return%20a.default.langs%5Bt%5D%5Be%5D%7Dcatch(n)%7Breturn%20console.error(%22%5Binstantgram%5DLOC%20error:%22,n),%22ops,%20an%20error%20ocurred%20in%20localization%20system.%20Enter%20in%20https://github.com/theus/instantgram/issues/new%20and%20open%20an%20issue%20with%20this%20code:%20'LOC_dont_found_str_neither_default:%5B%22+t+%22-%3E%22+e+%22%5D'%5Cn%20%20%20%20for%20more%20information%20open%20the%20console%22%7D%7Dconsole.info(o(%22helpers.localize_defaultlang%22).replace(%22$%7BLANG_DEFAULT%7D%22,r)),t.default=o%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=%7Blangs:%7B%22de-DE%22:%7B%22helpers.localize_defaultlang%22:%22Ausgew%C3%A4hlte%20Sprache:%20$%7BLANG_DEFAULT%7D%20%5Cn%20Weitere%20Informationen%20zu%20den%20unterst%C3%BCtzten%20Sprachen%20findest%20du%20auf%20http://theus.github.io/instantgram%22,%22modules.update@oudated_outdated%22:%22%5Binstantgram%5D%20ist%20veraltet.%20Bitte%20besuche%20die%20Seite%20http://theus.github.io/instantgram%20f%C3%BCr%20ein%20Update.%22,%22modules.update@oudated_localInfo%22:%22%5Binstantgram%5D%20Installierte%20Version%20$%7Bdata.version%7D%20%7C%20Neue%20Version:%20$%7Bdata.gitVersion%7D%22,%22modules.update@determineIfGetUpdateIsNecessary_contacting%22:%22%5Binstantgram%5D%20sucht%20nach%20neuen%20verf%C3%BCgbaren%20Updates%E2%80%A6%22,%22modules.update@determineIfGetUpdateIsNecessary_updated%22:%22%5Binstantgram%5D%20wurde%20aktualisiert.%22,%22modules.update@determineIfGetUpdateIsNecessary_@alert_found%22:%22%5Binstantgram%5D%20hat%20ein%20neues%20Update%20gefunden.%5CnBitte%20besuche%20die%20Seite%20http://theus.github.io/instantgram,%20um%20das%20Update%20zu%20installieren.%22,%22index@alert_onlyWorks%22:%22%5Binstantgram%5D%20funktioniert%20nur%20mit%20instagram.com.%22,%22index#program#modal@alert_dontFound%22:%22%5Binstantgram%5D%20konnte%20kein%20Bild%20in%20diesem%20Post%20finden.%20Bitte%20%C3%B6ffne%20den%20Link%20in%20einem%20neuen%20Tab.%22,%22index#program#post@alert_dontFound%22:%22Ops,%20%5Binstantgram%5D%20konnte%20leider%20kein%20Bild%20finden%20%20:-(%22,%22index#program#screen@alert_dontFound%22:%22%5Binstantgram%5D%20hat%20mehr%20als%201%20Bild%20gefunden.%20Bist%20du%20in%20der%20Profilansicht?%20Falls%20ja,%20%C3%B6ffne%20bitte%20zuerst%20einen%20einzelnen%20Post%20und%20f%C3%BChre%20%5Binstantgram%5D%20erneut%20aus.%22,%22index#program@alert_dontFound%22:%22Ops,%20hast%20du%20einen%20Instagram%20Post%20ge%C3%B6ffnet?%20Zum%20Beispiel%20instagram.com/p/82jd828jd%22%7D,%22en-US%22:%7B%22helpers.localize_defaultlang%22:%22%5Binstantgram%5D%20set%20language:%20$%7BLANG_DEFAULT%7D%20%5Cn%20For%20more%20information%20about%20available%20languages%20please%20check%20http://theus.github.io/instantgram%22,%22modules.update@oudated_outdated%22:%22%5Binstantgram%5D%20is%20outdated.%20Please%20check%20http://theus.github.io/instantgram%20for%20available%20updates.%22,%22modules.update@oudated_localInfo%22:%22%5Binstantgram%5D%20Installed%20version:%20$%7Bdata.version%7D%20%7C%20New%20update:%20$%7Bdata.gitVersion%7D%22,%22modules.update@determineIfGetUpdateIsNecessary_contacting%22:%22%5Binstantgram%5D%20is%20looking%20for%20available%20updates%E2%80%A6%22,%22modules.update@determineIfGetUpdateIsNecessary_updated%22:%22%5Binstantgram%5D%20updated%20your%20current%20version.%22,%22modules.update@determineIfGetUpdateIsNecessary_@alert_found%22:%22%5Binstantgram%5D%20found%20a%20new%20available%20update.%5CnPlease%20check%20http://theus.github.io/instantgram%20to%20install%20it.%22,%22index@alert_onlyWorks%22:%22%5Binstantgram%5D%20only%20works%20on%20instagram.com.%22,%22index#program#modal@alert_dontFound%22:%22%5Binstantgram%5D%20didn't%20find%20any%20image%20in%20this%20Instagram%20post.%20Please%20try%20to%20open%20the%20link%20in%20a%20new%20tab.%22,%22index#program#post@alert_dontFound%22:%22Ops,%20%5Binstantgram%5D%20couldn't%20find%20any%20image%20%20:-(%22,%22index#program#screen@alert_dontFound%22:%22%5Binstantgram%5D%20found%20more%20than%201%20image.%20Are%20you%20on%20a%20profile%20page?%20If%20yes,%20please%20open%20a%20single%20post%20first%20and%20open%20%5Binstantgram%5D%20again.%22,%22index#program@alert_dontFound%22:%22Ops,%20did%20you%20open%20any%20Instagram%20post?%20Like%20for%20example%20instagram.com/p/82jd828jd%22%7D,%22es-AR%22:%7B%22helpers.localize_defaultlang%22:%22%5Binstantgram%5D%20elegir%20idioma:%20$%7BLANG_DEFAULT%7D%20%5Cn%20Para%20m%C3%A1s%20informaci%C3%B3n%20acerca%20de%20los%20idiomas%20disponibles,%20por%20favor%20visite%20http://theus.github.io/instantgram%22,%22modules.update@oudated_outdated%22:%22%5Binstantgram%5D%20est%C3%A1%20desactualizado.%20Por%20favor%20visite%20http://theus.github.io/instantgram%20para%20ver%20actualizaciones.%22,%22modules.update@oudated_localInfo%22:%22%5Binstantgram%5D%20Versi%C3%B3n%20instalada:%20$%7Bdata.version%7D%20%7C%20Nueva%20actualizaci%C3%B3n:%20$%7Bdata.gitVersion%7D%22,%22modules.update@determineIfGetUpdateIsNecessary_contacting%22:%22%5Binstantgram%5D%20est%C3%A1%20buscando%20nuevas%20actualizaciones%E2%80%A6%22,%22modules.update@determineIfGetUpdateIsNecessary_updated%22:%22%5Binstantgram%5D%20actualiz%C3%B3%20a%20la%20versi%C3%B3n%20actual.%22,%22modules.update@determineIfGetUpdateIsNecessary_@alert_found%22:%22%5Binstantgram%5D%20encontr%C3%B3%20una%20nueva%20actualizaci%C3%B3n%20disponible.%5CnPor%20favor%20visite%20http://theus.github.io/instantgram%20para%20instalarla.%22,%22index@alert_onlyWorks%22:%22%5Binstantgram%5D%20s%C3%B3lo%20funciona%20en%20instagram.com.%22,%22index#program#modal@alert_dontFound%22:%22%5Binstantgram%5D%20no%20encontr%C3%B3%20ninguna%20imagen%20en%20esta%20publicaci%C3%B3n%20de%20Instagram.%20Por%20favor%20intente%20abrir%20el%20link%20en%20una%20nueva%20pesta%C3%B1a.%22,%22index#program#post@alert_dontFound%22:%22Ups,%20%5Binstantgram%5D%20no%20pudo%20encontrar%20ninguna%20imagen%20:-(%22,%22index#program#screen@alert_dontFound%22:%22%5Binstantgram%5D%20encontr%C3%B3%20m%C3%A1s%20de%201%20imagen.%20%C2%BFEst%C3%A1s%20en%20una%20p%C3%A1gina%20de%20perfil?%20Si%20es%20as%C3%AD,%20por%20favor%20ingresa%20en%20una%20publicaci%C3%B3n%20y%20luego%20abre%20%5Binstantgram%5D%20nuevamente.%22,%22index#program@alert_dontFound%22:%22Ups,%20abriste%20alguna%20publicaci%C3%B3n%20de%20Instagram?%20Por%20ejemplo%20instagram.com/p/82jd828jd%22%7D,%22pt-BR%22:%7B%22helpers.localize_defaultlang%22:%22%5Binstantgram%5D%20idioma%20configurado:%20$%7BLANG_DEFAULT%7D%20%5Cnpara%20mais%20informa%C3%A7%C3%B5es%20sobre%20os%20idiomas%20suportados,%20acesse%20http://theus.github.io/instantgram%22,%22modules.update@oudated_outdated%22:%22%5Binstantgram%5D%20est%C3%A1%20desatualizado.%20Acesse%20http://theus.github.io/instantgram%20para%20atualizar%22,%22modules.update@oudated_localInfo%22:%22%5Binstantgram%5D%20vers%C3%A3o%20local:%20$%7Bdata.version%7D%20%7C%20nova%20vers%C3%A3o:%20$%7Bdata.gitVersion%7D%22,%22modules.update@determineIfGetUpdateIsNecessary_contacting%22:%22%5Binstantgram%5D%20est%C3%A1%20procurando%20atualiza%C3%A7%C3%B5es...%22,%22modules.update@determineIfGetUpdateIsNecessary_updated%22:%22%5Binstantgram%5D%20informa%C3%A7%C3%B5es%20locais%20atualizadas%22,%22modules.update@determineIfGetUpdateIsNecessary_@alert_found%22:%22%5Binstantgram%5D%20encontrou%20uma%20atualiza%C3%A7%C3%A3o.%5Cn%20acesse%20theus.github.io/instantgram%20para%20atualizar%22,%22index@alert_onlyWorks%22:%22%5Binstantgram%5D%20somente%20funciona%20no%20instagram.com%22,%22index#program#modal@alert_dontFound%22:%22%5Binstantgram%5D%20n%C3%A3o%20encontrou%20uma%20imagem%20em%20um%20post.%20Tente%20abrir%20o%20link%20em%20uma%20nova%20aba.%22,%22index#program#post@alert_dontFound%22:%22ops,%20%5Binstantgram%5D%20n%C3%A3o%20encontrou%20a%20imagem%20:(%22,%22index#program#screen@alert_dontFound%22:%22%5Binstantgram%5D%20a%20procura%20por%20imagem%20na%20tela%20encontrou%20mais%20de%201%20imagem.%20Voc%C3%AA%20est%C3%A1%20em%20um%20perfil?%20Se%20sim,%20abra%20alguma%20imagem%20antes%20de%20rodar%20o%20%5Binstantgram%5D%22,%22index#program@alert_dontFound%22:%22ops,%20voc%C3%AA%20est%C3%A1%20em%20algum%20post%20do%20instagram?%20ex:%20instagram.com/p/82jd828jd%22%7D%7D%7D%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Breturn(0,a.default)(e).filter(function(e)%7Breturn%22ARTICLE%22===e.nodeName%7D).length%3E0%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(1))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Be:if(1!==document.querySelectorAll(%22main%20%3E%20section%22).length);else%7Bvar%20n,r,o=document.querySelector(%22main%20%3E%20section%22),i=o.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20article%22);n=i.length%3E1?3==i.length?i%5BMath.floor(i.length/2)%5D:2==i.length?1==document.getElementsByClassName(%22coreSpriteLeftChevron%22).length?i.reverse().shift():i.reverse().pop():i%5BMath.floor(i.length/2)%5D:o.querySelectorAll(%22video%22);var%20s=%5B%5D.concat(function(e)%7Bif(Array.isArray(e))%7Bfor(var%20t=0,n=Array(e.length);t%3Ce.length;t++)n%5Bt%5D=e%5Bt%5D;return%20n%7Dreturn%20Array.from(e)%7D(n.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20ul:first-child%20%3E%20li%22))).filter(function(e)%7Breturn%20null!=e.firstChild&&e.classList.length%3E0%7D);s.length%3E1?(3==s.length?r=s%5BMath.floor(s.length/2)%5D:2==s.length&&(r=1==document.getElementsByClassName(%22coreSpriteLeftChevron%22).length?s.reverse().shift():s.reverse().pop()),r=r.querySelectorAll(%22video%22)):r=o.querySelectorAll(%22video%22);for(var%20l=0,l=0;l%3Cr.length;l++)if((0,a.default)(r%5Bl%5D))%7Bvar%20d=r%5Bl%5D.src;if(d)%7Bif(-1!==d.indexOf(%22blob:%22))%7Be.context=%7BhasMsg:!0,msg:%22index#program@alert_videoBlob%22%7D;break%20e%7Dwindow.open(d),t=!0,e.foundVideo=!0,e.foundByModule=%22searchVideoInPage%22,e.alertNotInInstagramPost=!0%7D%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchVideoInPage()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(0))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Bif(e.regexStoriesURI.test(e.path))%7Bvar%20n=document.getElementById(%22react-root%22),a=n.querySelectorAll(%22video%20%3E%20source%22),r=n.querySelectorAll(%22img%5Bsrcset%5D%22),o=%22%22;if(a.length%3E0?o=a%5B0%5D.src:1==r.length&&(o=r%5B0%5D.src),o&&(e.setImageLink(o),window.open(e.imageLink),t=!0,e.foundImage=!0,e.foundByModule=%22searchImageVideoInStories%22),!1===t&&e.videos.length%3E0)%7Bvar%20i=e.videos%5B0%5D.src;!i&&e.videos%5B0%5D.children&&(i=e.videos%5B0%5D.children%5B0%5D.src),i&&(window.open(i),t=!0,e.foundVideo=!0,e.alertNotInInstagramPost=!0,e.foundByModule=%22searchImageVideoInStories%22)%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchImageVideoInStories()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;!function(e)%7Be&&e.__esModule%7D(n(2))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Be:if(1!==document.getElementsByTagName(%22article%22).length);else%7Bvar%20n,r=document.querySelector(%22article%22),o=%5B%5D.concat(function(e)%7Bif(Array.isArray(e))%7Bfor(var%20t=0,n=Array(e.length);t%3Ce.length;t++)n%5Bt%5D=e%5Bt%5D;return%20n%7Dreturn%20Array.from(e)%7D(r.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20ul:first-child%20%3E%20li%22))).filter(function(e)%7Breturn%20null!=e.firstChild&&e.classList.length%3E0%7D);o.length%3E1?(3==o.length?n=o%5BMath.floor(o.length/2)%5D:2==o.length&&(n=1==document.getElementsByClassName(%22coreSpriteLeftChevron%22).length?o.reverse().shift():o.reverse().pop()),n=n.querySelectorAll(%22video%22)):n=r.querySelectorAll(%22video%22);for(var%20i=0,i=0;i%3Cn.length;i++)if((0,a.default)(n%5Bi%5D))%7Bvar%20s=n%5Bi%5D.src;if(s)%7Bif(-1!==s.indexOf(%22blob:%22))%7Be.context=%7BhasMsg:!0,msg:%22index#program@alert_videoBlob%22%7D;break%20e%7Dwindow.open(s),t=!0,e.foundVideo=!0,e.foundByModule=%22searchVideoInPost%22,e.alertNotInInstagramPost=!0%7D%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchVideoInPost()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(0))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Be:if(2!==document.getElementsByTagName(%22article%22).length);else%7Bvar%20n,r=document.getElementsByTagName(%22article%22)%5B1%5D,o=%5B%5D.concat(function(e)%7Bif(Array.isArray(e))%7Bfor(var%20t=0,n=Array(e.length);t%3Ce.length;t++)n%5Bt%5D=e%5Bt%5D;return%20n%7Dreturn%20Array.from(e)%7D(r.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20ul:first-child%20%3E%20li%22))).filter(function(e)%7Breturn%20null!=e.firstChild&&e.classList.length%3E0%7D);o.length%3E1?(3==o.length?n=o%5BMath.floor(o.length/2)%5D:2==o.length&&(n=1==document.getElementsByClassName(%22coreSpriteLeftChevron%22).length?o.reverse().shift():o.reverse().pop()),n=n.querySelectorAll(%22video%22)):n=r.querySelectorAll(%22video%22);for(var%20i=0,i=0;i%3Cn.length;i++)if((0,a.default)(n%5Bi%5D))%7Bvar%20s=n%5Bi%5D.src;if(s)%7Bif(-1!==s.indexOf(%22blob:%22))%7Be.context=%7BhasMsg:!0,msg:%22index#program@alert_videoBlob%22%7D;break%20e%7Dwindow.open(s),t=!0,e.foundVideo=!0,e.foundByModule=%22searchVideoInModalPost%22,e.alertNotInInstagramPost=!0%7D%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchVideoInModalPost()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(0))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Bif(1!==document.querySelectorAll(%22main%20%3E%20section%22).length);else%7Bfor(var%20n,r=document.querySelector(%22main%20%3E%20section%22),o=r.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20article%22),i=0;i%3Co.length;i++)if((0,a.default)(o%5Bi%5D))%7Bvar%20s=o%5Bi%5D.querySelector(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20img%22);s&&(n=s.src);break%7Dvar%20l,d=%5B%5D.concat(function(e)%7Bif(Array.isArray(e))%7Bfor(var%20t=0,n=Array(e.length);t%3Ce.length;t++)n%5Bt%5D=e%5Bt%5D;return%20n%7Dreturn%20Array.from(e)%7D(o%5Bi%5D.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20ul:first-child%20%3E%20li%22))).filter(function(e)%7Breturn%20null!=e.firstChild&&e.classList.length%3E0%7D);d&&d.length%3E1&&(3==d.length?l=d%5BMath.floor(d.length/2)%5D:2==d.length&&(l=1==o%5Bi%5D.querySelector(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%22).getElementsByClassName(%22coreSpriteLeftChevron%22).length?d.reverse().shift():d.reverse().pop()),l=l.querySelector(%22img%5Bsrcset%5D%22),n=l.src),e.setImageLink(n),e.imageLink?(window.open(e.imageLink),t=!0,e.foundByModule=%22searchImageInPage%22):e.context=%7BhasMsg:!0,msg:%22index#program#post@alert_dontFound%22%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchImageInPage()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;var%20a=r(n(0));r(n(1)),r(n(12)),r(n(13));function%20r(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Breturn%22a%22===e.parentElement.localName%7C%7C(0,a.default)(e).filter(function(e)%7Breturn%22HEADER%22===e.nodeName%7D).length%3E0%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(1))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Breturn%22SPAN%22===e.parentElement.nodeName&&%22link%22===e.parentElement.getAttribute(%22role%22)%7D;!function(e)%7Be&&e.__esModule%7D(n(1))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Bif(1===document.getElementsByTagName(%22article%22).length)%7Bvar%20n,r=document.querySelector(%22article%22),o=%5B%5D.concat(function(e)%7Bif(Array.isArray(e))%7Bfor(var%20t=0,n=Array(e.length);t%3Ce.length;t++)n%5Bt%5D=e%5Bt%5D;return%20n%7Dreturn%20Array.from(e)%7D(r.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20ul:first-child%20%3E%20li%22))).filter(function(e)%7Breturn%20null!=e.firstChild&&e.classList.length%3E0%7D);o.length%3E1?(3==o.length?n=o%5BMath.floor(o.length/2)%5D:2==o.length&&(n=1==document.getElementsByClassName(%22coreSpriteLeftChevron%22).length?o.reverse().shift():o.reverse().pop()),n=n.querySelectorAll(%22img%5Bsrcset%5D%22)):n=r.querySelectorAll(%22img%5Bsrcset%5D%22);for(var%20i=0,i=0;i%3Cn.length;i++)if((0,a.default)(n%5Bi%5D))%7Bvar%20s=n%5Bi%5D.src;s?(window.open(s),e.foundImage=!0,t=!0,e.foundByModule=%22searchImageInPost%22):e.context=%7BhasMsg:!0,msg:%22index#program#screen@alert_dontFound%22%7D,e.alertNotInInstagramPost=!1%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchImageInPost()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(0))%7D,function(e,t,n)%7B%22use%20strict%22;Object.defineProperty(t,%22__esModule%22,%7Bvalue:!0%7D),t.default=function(e)%7Bvar%20t=!1;try%7Bif(2===document.getElementsByTagName(%22article%22).length)%7Bvar%20n,r=document.getElementsByTagName(%22article%22)%5B1%5D,o=%5B%5D.concat(function(e)%7Bif(Array.isArray(e))%7Bfor(var%20t=0,n=Array(e.length);t%3Ce.length;t++)n%5Bt%5D=e%5Bt%5D;return%20n%7Dreturn%20Array.from(e)%7D(r.querySelectorAll(%22div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20div%20%3E%20ul:first-child%20%3E%20li%22))).filter(function(e)%7Breturn%20null!=e.firstChild&&e.classList.length%3E0%7D);o.length%3E1?(3==o.length?n=o%5BMath.floor(o.length/2)%5D:2==o.length&&(n=1==document.getElementsByClassName(%22coreSpriteLeftChevron%22).length?o.reverse().shift():o.reverse().pop()),n=n.querySelectorAll(%22img%5Bsrcset%5D%22)):n=r.querySelectorAll(%22img%5Bsrcset%5D%22);for(var%20i=0,i=0;i%3Cn.length;i++)if((0,a.default)(n%5Bi%5D))%7Bvar%20s=n%5Bi%5D.src;s?(window.open(s),e.foundImage=!0,t=!0,e.foundByModule=%22searchImageInModalPost%22):e.context=%7BhasMsg:!0,msg:%22index#program#modal@alert_dontFound%22%7D%7D%7D%7Dcatch(t)%7Bconsole.error(%22searchImageInModalPost()%22,%22%5Binstantgram%5D%20%22+e.VERSION,t)%7Dreturn%20t%7D;var%20a=function(e)%7Breturn%20e&&e.__esModule?e:%7B%22default%22:e%7D%7D(n(0))%7D%5D);})()
```

### GitHub Repository
<a href='javascript:void(window.location.href=window.location.protocol+"//github.com/"+window.location.host.split(".")[0]+"/"+window.location.pathname.split("/")[1])'>bookmark</a>
```js
window.location.href = window.location.protocol +
  "//github.com/" + window.location.host.split(".")[0] +
  "/" + window.location.pathname.split("/")[1]
```

### Github Website
<a href='javascript:void(window.location.href=window.location.protocol+"//"+window.location.pathname.split("/")[1]+".github.io/"+window.location.pathname.split("/")[2]+"/")'>bookmark</a>
```js
window.location.href = window.location.protocol +
  "//" + window.location.pathname.split("/")[1] +
  ".github.io/" + window.location.pathname.split("/")[2] + "/"
```

### Parse goodreads for Simulibros

```js
javascript:
image = document.querySelector("#coverImage").src;
rating = document.querySelector("[itemprop=ratingValue]").textContent.trim();
year = document.querySelector("#details .row:nth-child(2)").textContent.trim().slice(-4);
link = location.href;
serie = document.querySelector("#bookSeries a").textContent.trim();
author = document.querySelector("a.authorName [itemprop=name]").textContent;
title = document.querySelector("#bookTitle").textContent.trim();
hash = "title=" + title + "%20" + serie + "&author=" + author + "&year=" + year + "&link=" + link + "&rating=" + rating + "&image_url=" + image;
window.location = "https://petrosh.github.io/simulibros/add_book?a=" + btoa(hash);
```

```js
javascript:(function()%7Bjavascript%3A%0Aimage%20%3D%20document.querySelector(%22%23coverImage%22).src%3B%0Arating%20%3D%20document.querySelector(%22%5Bitemprop%3DratingValue%5D%22).textContent.trim()%3B%0Ayear%20%3D%20document.querySelector(%22%23details%20.row%3Anth-child(2)%22).textContent.trim().slice(-4)%3B%0Alink%20%3D%20location.href%3B%0Aserie%20%3D%20document.querySelector(%22%23bookSeries%20a%22).textContent.trim()%3B%0Aauthor%20%3D%20document.querySelector(%22a.authorName%20%5Bitemprop%3Dname%5D%22).textContent%3B%0Atitle%20%3D%20document.querySelector(%22%23bookTitle%22).textContent.trim()%3B%0Ahash%20%3D%20%22title%3D%22%20%2B%20title%20%2B%20%22%2520%22%20%2B%20serie%20%2B%20%22%26author%3D%22%20%2B%20author%20%2B%20%22%26year%3D%22%20%2B%20year%20%2B%20%22%26link%3D%22%20%2B%20link%20%2B%20%22%26rating%3D%22%20%2B%20rating%20%2B%20%22%26image_url%3D%22%20%2B%20image%3B%0Awindow.location%20%3D%20%22https%3A%2F%2Fpetrosh.github.io%2Fsimulibros%2Fadd_book%3Fa%3D%22%20%2B%20btoa(hash)%3B%7D)()%3B
```

### Archive.org Check page
```js
javascript:void(window.location.href='https://web.archive.org/web/*/'+location.href.replace(/\/$/,%20''))
```

### Archive Org Save
```js
javascript:l='https://archive.org';if(location.origin!=l)location=l+"/web/#"+location.href;else{if(document.getElementById('web_save_url')){document.getElementById('web_save_url').value=window.location.hash.slice(1);document.getElementById('web_save_button').click()}}
```

{% include footer.md %}
