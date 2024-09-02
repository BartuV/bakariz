<script>
	import {
		Navbar,
		NavBrand,
		NavLi,
		NavUl,
		NavHamburger,
		Avatar,
		Dropdown,
		DropdownItem,
		DropdownHeader,
		DropdownDivider,
	} from "flowbite-svelte";
	import "./app.css"
	import { page } from '$app/stores';

	$: activeUrl = $page.url.pathname;
</script>

<Navbar>
	<NavBrand href="/">
		<img
			src="src\images\channels4_profile.jpg"
			class="me-3 h-6 sm:h-9 rounded-full"
			alt="fantastikam Logo"
		/>
		<span
			class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"
			>fanstastikam</span
		>
	</NavBrand>
	<div class="flex items-center md:order-2">
		<Avatar id="avatar-menu" src="src\images\channels4_profile.jpg" />
		<NavHamburger class1="w-full md:flex md:w-auto md:order-1" />
	</div>
	<Dropdown placement="bottom" triggeredBy="#avatar-menu" arrow={true} shadow={true}>
		<DropdownHeader>
			<span class="block text-sm">Bonnie Green</span>
			<span class="block truncate text-sm font-medium"
				>name@flowbite.com</span
			>
		</DropdownHeader>
		<DropdownItem>Dashboard</DropdownItem>
		<DropdownItem>Settings</DropdownItem>
		<DropdownItem>Earnings</DropdownItem>
		<DropdownDivider />
		<DropdownItem>Sign out</DropdownItem>
	</Dropdown>
	<NavUl activeUrl={activeUrl}>
		<NavLi href="/">Home</NavLi>
		<NavLi href="/about">About</NavLi>
		<NavLi href="/docs/components/navbar">Navbar</NavLi>
		<NavLi href="/pricing">Pricing</NavLi>
		<NavLi href="/contact">Contact</NavLi>
	</NavUl>
</Navbar>

<slot/>