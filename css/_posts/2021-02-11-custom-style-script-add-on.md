---
tags: [adblock]
---
```css
/* https://www.duckduckgo.com */
.result__snippet{
  font-size:1.2em;
}
#ads, #zero_click_wrapper{
  display:none;
}
/* https://www.reddit.com/ */
a.thumbnail img {
    width: 200px;
    height: auto;
}
a.comments:visited{
  color: orange;
}
.thumbnail {
    width: 200px;
    max-height:none;
}
.promoted,
.organic-listing,
.trending-subreddits,
.happening-now,
.side
{
    display: none;
}
.promotedlink{
  display:none;
}
/* https://beta.observablehq.com/ */
.flex > .mw8 {
    border-right: 1px solid rgba(0,0,0,0.05);
}
.pointer.relative:last-child {
    background-color: #f7f7f9;
}
/* https://observablehq.com/ */
.flex > .mw8 {
    border-right: 1px solid rgba(0,0,0,0.05);
}
.pointer.relative:last-child {
    background-color: #f7f7f9;
}
/* https://www.reddit.com/r/teslamotors/ */
a .thumbnail, div#siteTable div.thing a.thumbnail {
max-height: none;
}
.thumbnail {
max-height: none !important;
}
a.expand:hover{ background: yellow !important; }
/* https://www.reddit.com/r/vegan/ */
.thumbnail {
    max-width: none;
}
/* https://www.reddit.com/r/RoastMe/ */
.thumbnail{
  width: 200px;
  height: auto;
}
/* https://www.reddit.com/r/TheExpanse/ */
.thumbnail img{
  max-height: none;
}
/* https://www.reddit.com/r/space/ */
.thumbnail{
  max-height: none;
}
/* https://www.reddit.com/r/rpg/ */
.link .crosspost-preview-content .usertext-body .md{
font-size: inherit;
}
/* https://www.reddit.com/r/science/ */
.link .flat-list, .link .entry .tagline, .thing p.title {
  margin-left; 200px;
}
/* https://ashtanga.github.io/ */
.sums {
  /* font-size: small; */
  font-size: x-small;
}
/* https://codepen.io/ */
.CodeMirror-gutter.CodeMirror-linenumbers{
border-right: 1px solid white;
}
/* https://www.3bmeteo.com/ */
#main-sidebar,
[id^=outbrain]{
  visibility: hidden;
}
.mainheader, .hidden-xs, #newsbar_top{
  display:none;
}
/* https://www.reddit.com/r/spacex */
body:not(.embed) > .content{
margin-right:220px;
}
/* https://news.ycombinator.com/ */
.togg, .storylink { outline: none; }
td > a[href*="item"]:visited { color: lightsalmon; }
a[rel="nofollow"]:hover{ text-decoration: none; }
a.storylink:hover, a.morelink:hover{ text-decoration: underline; }
a:active{ opacity: 0.5; }
/* https://coffeescript-cookbook.github.io/ */
html, button, input, select, textarea{ font-weight: 400;}
/* https://www.ilfattoquotidiano.it/ */
div[style*="position: fixed; width: 100%;"]{
  display: none;
}
/* https://www.youtube.com/ */
#chatframe,
#masthead-ad,
[class*="ytd-banner"],
.ytd-display-ad-renderer {
  display: none;
}
#placeholder-area{
 background: hsl(50.2, 73.5%, 16.3%);
}
/* https://www.ansa.it/ */
#player-1,
.player,
.news-special-box{
  display:none;
}
/* http://www.protezionecivile.gov.it/ */
[aria-describedby='cdk-describedby-message-2']]{
cursor: pointer;
}
[aria-describedby='cdk-describedby-message-2']]:hover{
opacity:0.5;
}
[aria-describedby='cdk-describedby-message-2']]:active{
opacity:0;
}
/* https://github.com/ */
* {
  scrollbar-color: #1f6feb #0d1117;
  scrollbar-width: auto;
}
*::-webkit-scrollbar-track{
  background: #0d1117;
{
*::-webkit-scrollbar-thumb{
  background: #1f6feb;
}
*::-webkit-scrollbar{
  width: auto;
}
```

```js
// https://www.ilfattoquotidiano.it/
var myVar = setInterval(myTimer, 2000);
function myTimer() {
  var arr = document.querySelectorAll("*");
  for (const ar of arr) {
    ar.style.fontFamily = "sans";
    ar.style.fontWeight= "normal";
  }
  clearInterval(myVar);
  console.log("timer 1500");
};
```

{% include footer.md %}