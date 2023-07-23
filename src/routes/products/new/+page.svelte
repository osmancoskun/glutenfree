<script>
    import {
        Label,
        Input,
        InputAddon,
        ButtonGroup,
        Button,
        Select,
        Modal,
        MultiSelect,
    } from "flowbite-svelte";

    let product_name = "";
    let product_link = "";
    let product_brand = "";
    let product_category = "";
    let brands = [];
    let categories = [];
    let new_brand_modal = false;
    let new_category_modal = false;
    let new_alergen_modal = false;

    let countries = [
        { value: "gluten", name: "Gluten" },
        { value: "egg", name: "Egg" },
        { value: "milk", name: "France" },
    ];
    let alergens;
</script>

<div class="mx-auto max-w-2xl">
    <div class="mb-6">
        <Label for="product_name" class="block mb-2">Product Name</Label>
        <ButtonGroup class="w-full">
            <InputAddon>
                <i class="material-icons">shopping_cart</i>
            </InputAddon>
            <Input
                id="product_name"
                placeholder="Enter Product Name"
                bind:value={product_name}
            />
        </ButtonGroup>
    </div>
    <div class="mb-6">
        <Label for="product_name" class="block mb-2">Product Link</Label>
        <ButtonGroup class="w-full">
            <InputAddon>
                <i class="material-icons">shopping_cart</i>
            </InputAddon>
            <Input
                id="product_name"
                placeholder="Enter Product Link"
                bind:value={product_link}
            />
        </ButtonGroup>
    </div>

    <div class="mb-6">
        <Label for="product_name" class="block mb-2">Product Description</Label>
        <ButtonGroup class="w-full">
            <Input
                id="product_name"
                placeholder="Enter Product Link"
                bind:value={product_link}
            />
        </ButtonGroup>
    </div>

    <div class="mb-6">
        <Label>
            Select Category
            <div class="flex gap-2">
                <Select items={brands} bind:value={product_category} />
                <Button
                    class="w-56"
                    on:click={() => (new_category_modal = !new_category_modal)}
                >
                    New Category
                </Button>
            </div>
        </Label>
    </div>

    <div class="mb-6">
        <Label>
            Select Brand
            <div class="flex gap-2">
                <Select items={brands} bind:value={product_brand} />
                <Button
                    class="w-56"
                    on:click={() => (new_brand_modal = !new_brand_modal)}
                >
                    New Brand
                </Button>
            </div>
        </Label>
    </div>

    <div class="mb-6">
        <Label>Select Alergens</Label>
        <div class="flex gap-2">
            <div class="w-full">
                <MultiSelect items={countries} bind:value={alergens} />
            </div>
            <Button
                class="w-56"
                on:click={() => (new_alergen_modal = !new_alergen_modal)}
            >
                New Alergen
            </Button>
        </div>
    </div>
</div>

<Modal title="New Brand" bind:open={new_brand_modal} autoclose>
    new_brand_modal
</Modal>
<Modal title="New Category" bind:open={new_category_modal} autoclose>
    new_category_modal
</Modal>
<Modal title="New Alergen" bind:open={new_alergen_modal} autoclose>
    new_alergen_modal
</Modal>
