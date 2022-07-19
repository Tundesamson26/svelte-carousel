<script>
    import {slide, fade} from 'svelte/transition'; 
    import {elasticInOut} from 'svelte/easing';

  const gallery_items = [
    {
      url: "https://res.cloudinary.com/beswift/image/upload/v1650390102/photo-1649894222226-056a1a79d9fb_xlv73h.jpg",
      description: "Dog",
    },
    {
      url: "https://res.cloudinary.com/beswift/image/upload/v1650391131/photo-1648800475313-2bb7fbec8701_ae60yw.jpg",
      description: "Building",
    },
    {
      url: "https://res.cloudinary.com/beswift/image/upload/v1650391337/photo-1647067867267-e01d98462f3c_ugtnwe.jpg",
      description: "Staircase",
    },
    {
      url: "https://res.cloudinary.com/beswift/image/upload/v1650391490/photo-1644241687200-eadaf7601290_xcz2kh.jpg",
      description: "Staircase",
    },
  ];

  let currentSlideItem = 0;

  const nextImage = () => {
    currentSlideItem = (currentSlideItem + 1) % gallery_items.length;
  }

  const prevImage = () => {
    if (currentSlideItem != 0) {
        currentSlideItem = (currentSlideItem - 1) % gallery_items.length;
    } else {
        currentSlideItem = gallery_items.length - 1;
    }
  }
</script>


  {#each [gallery_items[currentSlideItem]] as item (currentSlideItem)}
    <img in:slide="{{ duration: 1000, easing: elasticInOut}}" out:fade src={item.url} alt={item.description} width={1000} height={600}/>
  {/each}

  <div class="carousel-buttons">
    <button class="btn" on:click={() => prevImage()}>Previous</button>
    <button class="btn" on:click={() => nextImage()}>Next</button>
</div>

<style>
    .btn {
        background-color: #0a0a0a;
        color: beige;
        padding: 5px;
        margin: 15px;
        cursor: pointer;
    }
</style>