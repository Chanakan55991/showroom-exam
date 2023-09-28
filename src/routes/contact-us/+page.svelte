<script lang="ts">
	import toast from 'svelte-french-toast';
	let email = '';
	let message = '';
	let submitDisabled = false;
	let submitBtnText = 'Submit';

	const onSubmit = async () => {
		submitDisabled = true;
		submitBtnText = 'Submitting';
		const data = new FormData();
		data.append('email', email);
		data.append('message', message);

		const response = await fetch('https://formspree.io/f/xqkvgayy', {
			method: 'POST',
			body: data,
			redirect: 'manual'
		});
		console.log(response);

		if (response.status != 0) {
			toast.error('An error occurred while submitting the form');
			submitDisabled = false;
			submitBtnText = 'Submit';
		} else {
			toast.success('Your message had been sent!');
			submitBtnText = 'Submitted!';
		}
	};
</script>

<div class="mx-auto flex flex-col items-center justify-center w-screen h-full">
	<div class="w-[min(65ch, 100%-8rem)]">
		<h1 class="text-4xl bg-[#0005D2] w-fit text-white px-2">Contact us!</h1>
		<div class="note text-white leading-[-1] mb-4 text-sm">
			<p class="px-[0.2rem] bg-[#D25500]">
				Feel free to contact us using the form below, we will get
			</p>
			<p class="px-[0.2rem] w-fit bg-[#D25500]">in touch with you shortly!</p>
		</div>

		<form on:submit|preventDefault={onSubmit} class="mt-4 flex flex-col">
			<label for="email">Email Address</label>
			<input
				type="email"
				class="p-2 border-black border-2 border-solid rounded-full"
				name="email"
				bind:value={email}
				placeholder="someone@domain.tld"
				required
			/>
			<label for="password" class="mt-2">Message</label>
			<textarea
				placeholder="What do you want to tell us?"
				class="p-2 border-black border-2 border-solid rounded-2xl"
				bind:value={message}
				name="message"
				rows="10"
				required
			/>
			<button
				type="submit"
				disabled={submitDisabled}
				contenteditable="true"
				bind:innerText={submitBtnText}
				class="bg-white disabled:bg-gray-200 p-2 border-black border-2 border-solid rounded-2xl mt-4"
				>Submit</button
			>
		</form>
	</div>
</div>
