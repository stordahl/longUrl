<script>
  let URL;
  let setURL;

  const shortenURL = async function(long_url) {  
    let response = await fetch('/.netlify/functions/shortenURL', {
      body: JSON.stringify({long_url: long_url}),
      method: 'POST',
      mode: 'no-cors'
    })
    let data = await response.json();
    return data;
  }

  const handleSubmit = async (event) => {
   event.preventDefault();
     if (URL !== ""){
       event.preventDefault();
       await shortenURL(URL).then(data => {
         alert(`http://`+window.location.hostname + `/`+ data.shorturl);
       })
     }
     else{
       alert(`Provide a valid URL`)
     }
 };
</script>

<form action="">
  <label for="url">
    <input type="text" name="url" bind:value={URL}>
  </label>
  <input type="button" value="shorten" on:click={handleSubmit}>
</form>

<style>
  form{
    margin:auto;
    text-align:center;
  }
</style>