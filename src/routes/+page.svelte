<script>
    import {Button, Container} from '@sveltestrap/sveltestrap';

    import logo from '$lib/assets/logo.svg';


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
        Form,
        FormGroup,
        Input,
        Label
    } from '@sveltestrap/sveltestrap';

    let isOpen = $state(false);

    function handleNavClick() {
        isOpen = !isOpen
    }

    function handleForm1ButtonClick() {
        alert("Ouch - you clicked me!")
    }

</script>



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


<!--<div class="container">-->
<Container>
    <div class="row">

        <div class="col-sm-12">
            <h1>Welcome to SvelteKit + Sveltestrap</h1>
            <p>
                hi there, from some Bootstrap styled stuff
            </p>

            <!-- ********************************* -->
            <hr/>
            <Form>
                <h2>User details</h2>
                <FormGroup class="--bs-primary-border-subtle">
                    <Label for="form1_username">Username</Label>
                    <Input type="text" class="form-control" id="form1_username" aria-describedby="emailHelp" placeholder="Enter email"/>
                </FormGroup>

                <Button id="form1_email" type="submit" color="primary" on:click={handleForm1ButtonClick}>
                    Click me
                </Button>
            </Form>
        </div>
    </div>
</Container>
<!--</div>-->
