<script lang="ts">
	interface Input {
		type?: string | 'email' | 'password';
		label?: string;
		id?: string;
		value?: any;
		placeholder?: string;
	}

	export let { id, label, value, type, placeholder }: Input = {};
</script>

<div class="flex w-full flex-col items-start">
	<label for={id}>{label}</label>
	<input
		id="email"
		class="w-full border-b border-black py-8 text-xl outline-none placeholder:text-xl placeholder:text-black"
		{type}
		{placeholder}
		{value}
	/>
</div>
