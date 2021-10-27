<script>
	const shuffleArray = array => 
{

  for (let i = array.length - 1; i > 0; i--) 
  {
    const j = Math.floor(Math.random() * (i + 1));
    const temp = array[i];
    array[i] = array[j];
    array[j] = temp;
  }
  
}
	let misteryBox = "A box that contains a random Waifu";
	let waifu = "You don`t have a waifu"
	let inventory = misteryBox
	let posibleWaifus = [10000,10001,10002,10003,10004]
	function openBox(){
		if(inventory==misteryBox){
			shuffleArray(posibleWaifus)
		return posibleWaifus[0]
		}else{
			return "You don`t have any mistery Box";
		}
	}
	let seed = openBox()
	let src = "https://thisanimedoesnotexist.ai/results/psi-0.3/seed"+seed+".png";
	let name = 'waifu';
	misteryBox = true
	function toggle(){
		misteryBox = false
	}
</script>
{#if misteryBox==true}
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRos8fy29m0dkiYqHDEN3vyD6BB-JJX2hqhjw&usqp=CAU" alt="caja misteriosa" on:click={toggle}>
{/if}
{#if misteryBox==!true}
<img src="{src}" alt="{name}">
{/if}