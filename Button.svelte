<script>
	export let text;
</script>

<style>
	button {
	  min-width: 112px;
	  background: #e50914;
	  color: #fff;
	  padding: 6px 25px;
	  text-transform: uppercase;
	  border: 1px solid #e50914;
	  border-radius: 2px;
	  font-size: 1.6rem;
	  cursor: pointer;
	}

	button:hover {
	  background: #f40612;
	}

	svg {
	  width: 1rem;
	  height: 1.2rem;
	  fill: #fff;
	}
</style>

<button>
	{text}
	<svg viewBox="0 0 6 12" xmlns="http://www.w3.org/2000/svg"><desc>chevron</desc><path d="M.61 1.312l.78-.624L5.64 6l-4.25 5.312-.78-.624L4.36 6z" fill="none" fill-rule="evenodd"></path></svg>
</button>