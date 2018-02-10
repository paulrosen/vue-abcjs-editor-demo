<template>
	<div class="hello">
		<h1>Vue Editor abcjs Demo</h1>
		<p>This is a simple app that uses a textarea to display some sheet music.</p>
		<p>The only addition to the standard vue-cli app's dependencies is:</p>
		<pre>npm install abcjs --save-dev</pre>
		<p>The only necessary code to make this work is:</p>
		<pre>import abcjs from "abcjs";
new abcjs.Editor("abc-source",
    {canvas_id: "paper"});</pre>

		<pre>&lt;textarea id="abc-source"&gt;&lt;/textarea&gt;
&lt;div id="paper"&gt;&lt;/div&gt;</pre>
		<textarea id="abc-source">{{tune}}</textarea>
		<div id="paper"></div>
	</div>
</template>

<script>
	import abcjs from "abcjs";

	export default {
		mounted: function () {
			new abcjs.Editor("abc-source", {canvas_id: "paper"});
		},
		name: 'hello',
		data () {
			return {
				tune: 'X:1\nT: Cooley\'s\nM: 4/4\nL: 1/8\nR: reel\nK: Emin\nD2|:"Em"EB{c}BA B2 EB|~B2 AB dBAG|"D"FDAD BDAD|FDAD dAFD|\n"Em"EBBA B2 EB|B2 AB defg|"D"afe^c dBAF|1"Em"DEFD E2 D2:|2"Em"DEFD E2 gf||\n|:"Em"eB B2 efge|eB B2 gedB|"D"A2 FA DAFA|A2 FA defg|\n"Em"eB B2 eBgB|eB B2 defg|"D"afe^c dBAF|1"Em"DEFD E2 gf:|2"Em"DEFD E4|]\n'
			}
		}
	}
</script>

<style>
	.hello {
		text-align: left;
	}
	#abc-source {
		width: 350px;
		height: 300px;
	}

	pre {
		border: 1px solid #888888;
		padding: 6px;
		border-radius: 4px;
		width: 350px;
	}

</style>
