<script lang="ts">
	import '../app.postcss';

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>
<div class="navbar flex flex-row bg-primary-500 p-3">
	
	<a href="https://github.com/ContainerOFAids/Mall" class=""><img src="https://cdn-icons-png.flaticon.com/512/25/25231.png" alt="" class=" aspect-square w-10 hover:bg-white rounded-full"></a>
	
	<div class=" justify-center flex flex-row gap-10 w-full">
		<a href="http://localhost:5173/" class="navbtn h2 hover:text-gray-300">Home</a>
		<a href="" class="navbtn h2 hover:text-gray-300">About Us</a>
		<a href="" class="navbtn h2 hover:text-gray-300">Profile</a>
	</div>
	
	<img src="" alt="">

</div>
<slot />
