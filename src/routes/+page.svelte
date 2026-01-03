<script>
    import {
        Button,
        Container,
        Form,
        FormGroup,
        Input,
        Label
    } from '@sveltestrap/sveltestrap';

    function handleForm1ButtonClick() {
        alert("Ouch - you clicked me!")
    }
</script>

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
                    <Input type="text" class="form-control" id="form1_username" aria-describedby="emailHelp" placeholder="Enter username"/>
                </FormGroup>

                <Button id="form1_email" type="submit" color="primary" on:click={handleForm1ButtonClick}>
                    Click me
                </Button>
            </Form>
        </div>
    </div>
</Container>
<!--</div>-->
