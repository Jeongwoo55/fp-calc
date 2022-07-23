<script>
	let q = 1;
	let p = 2;
    let decimal = 0b0;
    let binary = 0;
    let hex = 0x0;

    
    function binToDec() {
        
    }

	function setIEEE32() {
		q = 8
		p = 24
	}

	function setIEEE64() {
		q = 11
		p = 53
	}
</script>

<label name="q">
	q =<input type=number bind:value={q} min=1>
</label>

<label name="p">
	p =<input type=number bind:value={p} min=2>
</label>

<label>
	<button type=button on:click={setIEEE32}>IEEE 32 bit</button>
</label>

<label>
	<button type=button on:click={setIEEE64}>IEEE 64 bit</button>
</label>

<label>
    Binary:
    <textarea value={binary}></textarea>
</label>

<label>
    Decimal:
    <textarea value={decimal}></textarea>
</label>

<label>
    Hex:
    <textarea value={hex}></textarea>
</label>

<p>q = {q}</p>
<p>p = {p}</p>

<p>smallest positive normalized FP number greater than 1: {1 + Math.pow(2, -(p - 1))}</p>
<!-- <p>largest positive normalized FP number greater than 1: {1 + Math.pow(2, -(p - 1))}</p> -->
<p>Machine epsilon ε (gap between the above number and 1): {Math.pow(2, -(p - 1))}</p>
<p>E max: {(Math.pow(2,q) - 2)/2}</p>
<p>E max: {-(Math.pow(2,q) - 4)/2}</p>
<p>bias: {1 - Math.pow(2,q - 1)}</p>

<style>
	label { display: flex }
	input, p { margin: 6px }
</style>