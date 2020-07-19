<script>

</script>

<div class="quote-container">
  <blockquote>There is nothing permanent except change.</blockquote>
  <p>Heraclitus</p>
</div>

<div class="icon-container">
  <button>
    <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="twitter" class="svg-inline--fa fa-twitter fa-w-16" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
      <path fill="#6CADDE" d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path>
    </svg>
  </button>
</div>

<div class="icon-container right-align">
  <button>
    <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="redo" class="svg-inline--fa fa-redo fa-w-16" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
      <path fill="currentColor" d="M500.33 0h-47.41a12 12 0 0 0-12 12.57l4 82.76A247.42 247.42 0 0 0 256 8C119.34 8 7.9 119.53 8 256.19 8.1 393.07 119.1 504 256 504a247.1 247.1 0 0 0 166.18-63.91 12 12 0 0 0 .48-17.43l-34-34a12 12 0 0 0-16.38-.55A176 176 0 1 1 402.1 157.8l-101.53-4.87a12 12 0 0 0-12.57 12v47.41a12 12 0 0 0 12 12h200.33a12 12 0 0 0 12-12V12a12 12 0 0 0-12-12z"></path>
    </svg>
  </button>
</div>

<style>
.quote-container {
  grid-column: 1 / 3;
}
.quote-container > blockquote {
  color: #1C1013;
  border: 1px solid black;
 }
.quote-container > p {
  border: 1px solid red;

  text-align-last: right;
  padding-right: 2em;
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
/*MISC*/
/*----*/
svg {
  width: 40px;
}
.right-align {
  place-content: flex-end;
}
</style>