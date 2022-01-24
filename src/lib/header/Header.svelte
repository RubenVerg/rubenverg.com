<script lang="ts">
	import {
		Collapse,
		Navbar,
		NavbarToggler, 
		NavbarBrand,
		Nav,
		NavItem,
	} from 'sveltestrap';
	import MaybeNavLink from './MaybeNavLink.svelte';
	import ThemeSwitchButton from './ThemeSwitchButton.svelte';
	import { store as theme } from '$lib/DarkMode.svelte';

	let isOpen = false;
	const expand = 'md';
</script>

<Navbar color={$theme} {...($theme === 'dark' ? { dark: true } : { light: true })} {expand}>
	<NavbarBrand href='/'>RubenVerg</NavbarBrand>
	<NavbarToggler on:click={() => isOpen = !isOpen} />
	<Collapse {isOpen} navbar {expand} on:update={evt => isOpen = evt.detail}>
		<Nav class='ms-auto'>
			<MaybeNavLink href='/'>Home</MaybeNavLink>
			<MaybeNavLink href='/contact'>Contact</MaybeNavLink>
			<NavItem>
				<ThemeSwitchButton />
			</NavItem>
		</Nav>
	</Collapse>
</Navbar>

<style lang='scss'>

</style>
