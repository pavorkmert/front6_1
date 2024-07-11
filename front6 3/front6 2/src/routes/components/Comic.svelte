<script>
  import { onMount } from 'svelte';

  let comic = {
    safe_title: '',
    img: '',
    alt: '',
    year: '',
    month: '',
    day: ''
  };

  onMount(async () => {
    const email = "ma.petrov@innopolis.university"; 
    const urlParams = new URLSearchParams({ email });
    const comicIdUrl = `https://fwd.innopolis.university/api/hw2?${urlParams.toString()}`;

    try {
      const response = await fetch(comicIdUrl);
      if (!response.ok) throw new Error('Network response was not ok');
      const comicId = await response.text();

      const comicUrl = `https://fwd.innopolis.university/api/comic?id=${comicId.trim()}`;
      const comicResponse = await fetch(comicUrl);
      if (!comicResponse.ok) throw new Error('Network response was not ok');
      comic = await comicResponse.json();
    } catch (error) {
      console.error("Error fetching comic:", error);
    }
  });
</script>

<div id="comic">
  <h2>{comic.safe_title}</h2>
  <img src={comic.img} alt={comic.alt} />
  <p>{new Date(comic.year, comic.month - 1, comic.day).toLocaleDateString()}</p>
</div>

<style>
#comic {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  max-width: 600px;
  margin: 0 auto;
}
#comic img {
  max-width: 100%;
  height: auto;
  max-height: 600px;
}
#comic h2 {
  font-size: 1.5em;
  color: #615F5F;
}
#comic p {
  font-size: 1.2em;
  color: #495057;
}
</style>
