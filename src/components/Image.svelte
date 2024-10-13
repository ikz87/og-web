<script>
  let img_src = "/images/placeholder.png";
  let img_class = "";
  export let spacing = "12";
  export let footnote;
  export { img_src as src };
  export { img_class as class };
</script>

<div class={`h-full w-full p-4 overflow-hidden flex items-center justify-center ${img_class}`}>
  <div class="relative flex items-center justify-center h-full w-full">
    <img src={img_src} class={`w-full h-full object-cover hover:scale-[1.03] transition rounded`} 
      style="
      -webkit-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.40);
      -moz-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.40);
      box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.40);"
    />
    {#if footnote}
      <span class="absolute w-full bottom-0 left-1/2 text-center transform -translate-x-1/2 bg-black bg-opacity-50 text-white text-sm p-1 rounded">
        {footnote}
      </span>
    {/if}
  </div>
</div>

