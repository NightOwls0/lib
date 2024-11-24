<script>
	import Preview from '$lib/Preview.svelte';
	import Badge from '$lib/components/Badge.svelte';
	import Alert from '$lib/components/Alert.svelte';
	import Button from '$lib/components/Button.svelte';
	import Tabs from '$lib/components/Tabs/Tabs.svelte';
	import TabHeader from '$lib/components/Tabs/TabHeader.svelte';
	import TabItem from '$lib/components/Tabs/TabItem.svelte';
	import TabContent from '$lib/components/Tabs/TabContent.svelte';
	import TabPanel from '$lib/components/Tabs/TabPanel.svelte';
	import Modal from '$lib/components/Modal/Modal.svelte';
	import ModalContent from '$lib/components/Modal/ModalContent.svelte';

	let modalOpen = $state(false);
	function openModal() {
		modalOpen = true
	}
</script>

<div class="container mx-auto px-4 py-8">
	<h1 class="text-3xl font-bold">Components</h1>

	<Preview title="Alert">
		<Alert icon="T" title="Heads up!">You can add components to your app using the cli.</Alert>
		<br />
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

	<Preview title="Tabs">
		<Tabs active="General">
			<TabHeader>
				<TabItem name="General" />
				<TabItem name="SEO" />
				<TabItem name="Settings" />
			</TabHeader>
			<TabContent>
				<TabPanel name="General">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex sequi excepturi reiciendis?
					Totam necessitatibus nisi dignissimos voluptatem iure esse culpa sint asperiores commodi
					rem inventore, cupiditate libero officia dolorem adipisci iusto sed saepe quasi. Nemo,
					sunt. Provident quo sit exercitationem quaerat illum numquam? Incidunt facere quasi minus
					sint ea? Possimus.
				</TabPanel>
				<TabPanel name="SEO">
					dipisicing elit. Ex sequi excepturi reiciendis? Totam necessitatibus nisi dignissimos
					voluptatem iure esse culpa sint asperiores commodi rem inventore, cupiditate libero
					officia dolorem adipisci iusto sed saepe quasi. Nemo, sunt. Provident quo sit
					exercitationem quaerat illum numquam? Incidunt facere quasi minus sint ea? Possimus.
				</TabPanel>
				<TabPanel name="Settings">
					Lorem ipsum dolor sit amet consectetur adidsf asdfasdofijasdf asdfasdfasdf
				</TabPanel>
			</TabContent>
		</Tabs>
	</Preview>
	<Preview title="Modal">
		<Button onclick={openModal}>Open modal</Button>
		<Modal bind:open={modalOpen}>
			<ModalContent>
				This is modal content
			</ModalContent>
		</Modal>
		
	</Preview>
</div>
