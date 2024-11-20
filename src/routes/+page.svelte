<script>
	import Preview from '$lib/Preview.svelte'
	import Badge from '$lib/components/Badge.svelte';
	import Alert from '$lib/components/Alert.svelte';
	import Button from '$lib/components/Button.svelte'
</script>
<div class="mx-auto container py-8 px-4">
	<h1 class="text-3xl font-bold">Components</h1>

	<Preview title="Alert">
		<Alert icon="T" title="Heads up!">
			You can add components to your app using the cli.
		</Alert>
		<br/>
		<Alert variant="destructive" icon="T" title="Error">
			Your session has expired. Please log in again.
		</Alert>
	</Preview>

	<Preview title="Badge">
		<Badge>Default</Badge>
		<Badge variant="secondary">Secondary</Badge>
		<Badge variant="destructive">Destructive</Badge>
		<Badge variant="outline">Outline</Badge>
	</Preview>

	<Preview title="Button">
		<Button>Default</Button>
		<Button variant="secondary">Secondary</Button>
		<Button variant="outline">Outline</Button>
		<Button variant="ghost">Ghost</Button>
		<Button variant="link">Link</Button>
		<Button variant="destructive">Destructive</Button>

		<Button variant="primary" size="sm">Small</Button>
		<Button variant="primary" size="sm" icon>I</Button>
		<Button variant="primary" icon>I</Button>
	</Preview>

</div>

