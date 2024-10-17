<script>
  import { onMount } from 'svelte';
  import background from '$lib/images/graphs-bg.webp';
    import { Carousel, Thumbnails, Button, Indicator } from 'flowbite-svelte';
  import images from './research-carousel.json';
  let index = 0;
  let forward = true;
</script>
<div id="Research" class="snap-center snap-always bg-white justify-center items-center h-dvh w-full">
  <!-- Fixed background image -->
  <div class="fixed to-slide-down top-0 left-0 h-full w-full"  
    style="background-image: url({background}); background-size: cover; background-position: center;"></div>

  <div class="z-10 w-full h-full flex flex-row items-center justify-center">
    <div class="to-slide-left z-20 w-full m-10 mr-0 p-24 bg-black text-white text-xl text-justify border-white box-shadow rounded-xl">
      Texto sobre las investigaciones de la empresa.... Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium. Integer tincidunt. Cras dapibus. Vivamus elementum semper nisi. Aenean vulputate eleifend tellus. Aenean leo ligula, porttitor eu, consequat vitae, eleifend ac, enim. Aliquam lorem ante, dapibus in, viverra quis, feugiat a, tellus. Phasellus viverra nulla ut metus varius laoreet. Quisque rutrum. Aenean imperdiet. Etiam ultricies nisi vel augue. Curabitur ullamcorper ultricies nisi. Nam eget dui. Etiam rhoncus. Maecenas tempus, tellus eget condimentum rhoncus, sem quam semper libero, sit amet adipiscing sem neque sed ipsum. Nam quam nunc, blandit vel, luctus pulvinar, hendrerit id, lorem. Maecenas nec odio et ante tincidunt tempus. Donec vitae sapien ut libero venenatis faucibus. Nullam quis ante. Etiam sit amet orci eget eros faucibus tincidunt. Duis leo. Sed fringilla mauris sit amet nibh. Donec sodales sagittis magna. Sed consequat, leo eget bibendum sodales, augue velit cursus nunc,
    </div>
    <div class="to-slide-right h-full w-full p-2 items-center justify-center">
      <div class="h-full w-full py-4 -my-4 flex justify-center">
      <Carousel {images} let:Indicators let:Controls 
        style="
        height: 100%;
        aspect-ratio: 12/16;"
        class="border-8 z-20 border-black box-shadow"
        imgClass="z-20"
        >
          <Controls class="z-20 -mx-16"/>
          <Indicators let:selected let:index class="translate-y-14 box-shadow rounded-b-xl p-4 bg-black">
             <Indicator class="z-10 {selected ? 'scale-150' : 'scale-100 opacity-50'}">
      </Indicator>
          </Indicators>
</Carousel>
  </div>
  </div>
  </div>
  </div>

