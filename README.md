# lazyimgload
lazyimg is a javascript livrary to faster image load


	<img class="lazy" data-src="http://localhost/test/bigfile.jpg" src="load.gif" alt="">
	<img class="lazy" data-src="http://localhost/test/bigfile.jpg" src="load.gif" alt="">
	<img class="lazy" data-src="http://localhost/test/bigfile.jpg" src="load.gif" alt="">

	<script>

		window.onscroll = function(ev){
			lazyLoad();
		}

		function lazyLoad(){
			var lazyImage = document.getElementsByClassName('lazy');
			for(var i=0; i<lazyImage.length;i++){
				if(lazyImage[i].src.indexOf('load') > -1){
					if(elementInViewport(lazyImage[i])){
						lazyImage[i].setAttribute('src', lazyImage[i].getAttribute('data-src'))
					}
				}
			}
		}

		function elementInViewport(el){
			var rect = el.getBoundingClientRect();
			return (
				rect.top >= 0 &&
				rect.left >= 0 &&
				rect.bottom <= ( window.innerHeight || document.documentElement.clientHeight ) &&
				rect.right <= ( window.innerWidth || document.documentElement.clientWidth )
			)
		}
		
	</script>
