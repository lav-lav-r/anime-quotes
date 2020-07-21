<script>
import { onMount } from 'svelte';
import { slide } from 'svelte/transition';
import { quintOut } from 'svelte/easing';

let quote;
let btnRefresh;
onMount( () => {
  //Fetch Data
  // fetch('https://anime-chan.herokuapp.com/api/quotes/random')
  //   .then( (res) => {
  //     if(res.ok){
  //       return res.json();
  //     } else {
  //       console.log("Error!");
  //     };
  //   })
  //   .then( (data) => {
  //     quoteText = data[0].quote;
  //     character = data[0].character;
  //     animeTitle = data[0].anime;
  //   });

  setTimeout( () => {
    state = true;
  }, 1000);
});

let state = false;
function refresh(){
  state = false;
  btnRefresh.classList.remove("ani-rotate");
  setTimeout( () => {
    state = true;
    btnRefresh.classList.add("ani-rotate");
  }, 250);
};

let quoteText = "";
let character = "";
let animeTitle = "";
let tweetLink = "";
$: if(quoteText === "" || character === ""){
     tweetLink = `https://twitter.com/intent/tweet?hashtags=growth`;
   } else {
     tweetLink = `https://twitter.com/intent/tweet?hashtags=growth&text="${quoteText}" -${character}`;
   };
</script>

{#if state}
<div bind:this={quote} transition:slide="{{delay: 250, duration: 300, easing: quintOut}}" class="quote-container">
  <blockquote id="text">
    <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="quote-left" class="svg-inline--fa fa-quote-left fa-w-16" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
      <path fill="currentColor" d="M464 256h-80v-64c0-35.3 28.7-64 64-64h8c13.3 0 24-10.7 24-24V56c0-13.3-10.7-24-24-24h-8c-88.4 0-160 71.6-160 160v240c0 26.5 21.5 48 48 48h128c26.5 0 48-21.5 48-48V304c0-26.5-21.5-48-48-48zm-288 0H96v-64c0-35.3 28.7-64 64-64h8c13.3 0 24-10.7 24-24V56c0-13.3-10.7-24-24-24h-8C71.6 32 0 103.6 0 192v240c0 26.5 21.5 48 48 48h128c26.5 0 48-21.5 48-48V304c0-26.5-21.5-48-48-48z"></path>
    </svg>
    {quoteText}</blockquote>
  <p id="author">{character} <em>from</em> {animeTitle}</p>
</div>
{/if}

<div class="icon-container">
  <button class="ani-shake">
    <a id="tweet-quote" target="_blank" href={tweetLink}>
      <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="twitter" class="svg-inline--fa fa-twitter fa-w-16" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
        <path fill="#6CADDE" d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path>
      </svg>
    </a>
  </button>
</div>

<div class="icon-container right-align">
  <button bind:this={btnRefresh} on:click={refresh} id="new-quote" class="ani-rotate">
    <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="redo" class="svg-inline--fa fa-redo fa-w-16" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
      <path fill="#E53D00" d="M500.33 0h-47.41a12 12 0 0 0-12 12.57l4 82.76A247.42 247.42 0 0 0 256 8C119.34 8 7.9 119.53 8 256.19 8.1 393.07 119.1 504 256 504a247.1 247.1 0 0 0 166.18-63.91 12 12 0 0 0 .48-17.43l-34-34a12 12 0 0 0-16.38-.55A176 176 0 1 1 402.1 157.8l-101.53-4.87a12 12 0 0 0-12.57 12v47.41a12 12 0 0 0 12 12h200.33a12 12 0 0 0 12-12V12a12 12 0 0 0-12-12z"></path>
    </svg>
  </button>
</div>

<style>
.quote-container {
  grid-column: 1 / 3;
}
.quote-container > blockquote {
  color: var(--text);
  font-size: 2.25rem;
  font-weight: 400;
  margin-top: 0;
  margin-bottom: 1rem;
 }
.quote-container > p {
  text-align-last: right;
  padding-right: 2em;
  padding-bottom: 1rem;
  font-size: 1.25rem;
  font-weight: 300;
 }
.icon-container {
  display: flex;
  grid-row: 2 / 3;
 }
.icon-container > button {
  background: none;
  border: none;
  cursor: pointer;
}
.icon-container > .ani-shake:hover {
  animation: shake 400ms linear;
}
.icon-container > .ani-rotate {
  animation: rotate 400ms linear;
}
/*MISC*/
/*----*/
svg {
  width: 40px;
}
.right-align {
  place-content: flex-end;
}
/*Animation*/
/*---------*/
@keyframes shake {
  0%    {transform: rotate(0deg)  }
  25%   {transform: rotate(-10deg)}
  75%   {transform: rotate(10deg) }
  100%  {transform: rotate(0deg)  }
}
@keyframes rotate {
  0%    {transform: rotate(0deg)    }
  50%   {transform: rotate(180deg)  }
  100%  {transform: rotate(360deg)  }
}
/*Media Queries*/
/*-------------*/
@media screen and (max-width: 768px) {
  .quote-container > blockquote {
    font-size: 1.5rem;
  }
  .quote-container > p {
    font-size: 1rem;
  }
}
</style>