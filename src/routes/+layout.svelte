<script>
	import favicon from '$lib/assets/favicon.svg';
	import logo from '$lib/assets/logo.svg';

	import {Styles} from '@sveltestrap/sveltestrap';
	import {
		Collapse,
		NavbarToggler,
		NavbarBrand,
		Nav,
		Navbar,
		NavItem,
		NavLink,
		Dropdown,
		DropdownToggle,
		DropdownMenu,
		DropdownItem,
	} from '@sveltestrap/sveltestrap';

	let { children } = $props();

	let isOpen = $state(false);

	function handleNavClick() {
		isOpen = !isOpen
	}
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<Styles />
</svelte:head>



<!--see-->
<!--https://sveltestrap.js.org/?path=/docs/components-navbar&#45;&#45;docs-->

<Navbar color="dark" dark expand="md" container="md">
	<NavbarBrand href="/">
		<img src={logo} alt="module logo" width="100rem" />
		My Great Website !
	</NavbarBrand>

	<NavbarToggler on:click={handleNavClick} />

	<Collapse {isOpen} navbar expand="md">
		<!--        <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>-->
		<Nav class="ms-auto" navbar>
			<NavItem>
				<NavLink href="#components/">Components</NavLink>
			</NavItem>
			<NavItem>
				<NavLink href="https://github.com/sveltestrap/sveltestrap">GitHub</NavLink>
			</NavItem>
			<Dropdown nav inNavbar>
				<DropdownToggle nav caret>Options</DropdownToggle>
				<DropdownMenu end>
					<DropdownItem>Option 1</DropdownItem>
					<DropdownItem>Option 2</DropdownItem>
					<DropdownItem divider />
					<DropdownItem>Reset</DropdownItem>
				</DropdownMenu>
			</Dropdown>
		</Nav>
	</Collapse>
</Navbar>

{@render children()}
