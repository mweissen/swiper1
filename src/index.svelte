<script>
  /* Import Swiper and SwiperSlide components from .svelte files */
  import Swiper from "swiper/esm/svelte/swiper.svelte";
  import SwiperSlide from "swiper/esm/svelte/swiper-slide.svelte";

  import { Autoplay, Pagination, Navigation } from "swiper/core";

  import "swiper/swiper.min.css";
  import "swiper/components/pagination/pagination.min.css";
  import "swiper/components/navigation/navigation.min.css";

  const items = [
    {
      name: "Leonardo2",
      age: 26,
      location: "Italy"
    },
    {
      name: "Maria",
      age: 27,
      location: "Brazil"
    },
    {
      name: "Oliver",
      age: 28,
      location: "United States"
    },
    {
      name: "Margarida",
      age: 29,
      location: "Portugal"
    }
  ];
</script>

<Swiper 
  loop={true}
	spaceBetween={30}
	slidesPerView={2}
	autoplay={{
		delay: 1000,
		disableOnInteraction: false
	}}
	navigation={true}
  modules={[Autoplay, Navigation, Pagination]}
>
  {#each items as item, i}
    <SwiperSlide>
      <div style="padding: 30px 8px; text-align: center; background: #EEE; border-radius: 5px;">
        <strong>{item.name}</strong> ({item.age})
        from {item.location}
      </div>
    </SwiperSlide>
  {/each}
</Swiper>