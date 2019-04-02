# cute_dogs_images
This web application generates random photos of cute dogs on screen.
<html>
    <head>
<title>Cute Dogs</title>
 <link href="https://fonts.googleapis.com/css?family=ZCOOL+XiaoWei" rel="stylesheet">
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
      <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js">
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>

	  <style>
  body{
          background: #d1d1e0;
  font-family: 'ZCOOL XiaoWei', serif;
}
 h1 { 
  display: block;
  font-size: 5em;
  font-weight: bold;
}
</style>
    </head>
    <body>
        <div class="gallery-container">
		<center> <h1 class="text-primary">Cute Dogs</h1></center>
 <center><button type="submit" class="btn btn-primary" onclick=" window.location.reload()">See New Doggos</button></center>
        </div>
<script>
const numberOfDogs = 1; 
const dogsAvail = 100;
const $galleryContainer = document.querySelector('.gallery-container');
function renderGalleryItem(randomNumber){
  fetch(`https://source.unsplash.com/collection/212527/200*200/?sig=${randomNumber}`)
    .then((response)=> {    
      let galleryItem = document.createElement('div');
      galleryItem.classList.add('gallery-item');
      galleryItem.innerHTML = `
        <img class="gallery-image" src="${response.url}" />
      `
      $galleryContainer.appendChild(galleryItem);
    })
}
for(let i=0;i<numberOfDogs;i++){
  let randomImageIndex = Math.floor(Math.random() * dogsAvail);
  renderGalleryItem(randomImageIndex);
}
</script>
</body>
</html>
