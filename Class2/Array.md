<a href="#" class="load-more">
Load more 
	<span class="loading"><span></span></span>
	</a>
	
	
	
css

:root{
	--primary-color:#686de0;
	--white-color:#ffffff;
	--light-color:#f1f2f6;
	--gray-color:#b0b5bd;
	--dark-color:#353b48;
}


.load-more{
display:flex;
align-items:center;
justify-content:center;
font-size:14px;
width:180px;
height:52px;
text-transform:uppercase;
background-color:var(--dark-color)
color:var(--white-color);
margin:0 auto;
border-radius:30px;
transition:all .3s ease.out;
}
.load-more:hover{
background-color:var(--light-color);
color:inherit;
}

.loading{
display:block;
height:32px;
width:32px;
margin:0 auto;
animation:loader1 3s linear infinite;
}
@keyframs loader1{
from {transform: rotate(0deg);}
to{transform:rotate(360deg);}
}


.loading span{
display:block;
position:absolute;
top:0;
left:0;
bottom:0;
right:0;
width32[x
height:32px;
clip:rect(16px, 32px, 32px, 0);
animation:loader2 1.5s cubic-bezier(0.77, 0, 0.175, 1) infinite;
}
@keyframs loader2{
from {transform: rotate(0deg);}
to{transform:rotate(360deg);}
}

.leading span::before{
content:'';
display:block;
position:absolute;
top:0;
bottom:0;
right:0;
width:32px;
height:32px;
border:3px solid transparent;
border-top:3px solid var(--white-color);
border-radius:50%;
animation:loader3 1.5s cubic-bezier(0.77, 0, 0.175, 1) infinite;
}
@keyframs loader3{
from {transform: rotate(0deg);}
to{transform:rotate(360deg);}
}

.leading span::after{
content:'';
display:block;
position:absolute;
top:0;
bottom:0;
right:0;
width:32px;
height:32px;
border:3px solid transparent;
border:3px solid var(--primary-color);
border-radius:50%;
}




<script>

const loadmore = document.querySelector('.load-more');
	let currentItems = 3;
	loadmore.addEventListener('click', (e) => {
		const elementList = [...document.querySelectorAll('.post .post-box')];
		e.target.classList.ad('show-loader');
		
		for (let i = currentItems; i < currentItems + 3; i++){
			setTimeout(function()){
				e.target.classList.remove('show-loader');
				if(elementList[i]){
					elementList[i].style.display = 'flex';
				}
			}, 3000)
		}
		currentItems +=3;
		
		// hide load button after fully load
		if (currentItems => elementList.length){
			event.target.classList.add('loaded')
		}
	})			


</script>