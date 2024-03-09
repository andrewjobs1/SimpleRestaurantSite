<div>
    <ul class="grid grid-cols-2 w-2/3 m-auto md:grid-cols-4 gap-y-4">
        <li class="flex justify-center">
            <button on:click={(event) => handleClick(event, "dinner")} class="w-1/2 py-2 text-center font-semibold text-text-primary cursor-pointer hover:bg-primary-dark {dinnerActive ? 'bg-primary-dark': 'bg-primary'}">Dinner</button>
        </li>
        <li class="flex justify-center">
            <button on:click={(event) => handleClick(event, "lunch")} class= "w-1/2 py-2 text-center font-semibold text-text-primary cursor-pointer hover:bg-primary-dark {lunchActive ? 'bg-primary-dark': 'bg-primary'}">Lunch</button>
        </li>
        <li class="flex justify-center">
            <button on:click={(event) => handleClick(event, "brunch")} class="w-1/2 py-2 text-center font-semibold text-text-primary cursor-pointer hover:bg-primary-dark {brunchActive ? 'bg-primary-dark': 'bg-primary'}">Brunch</button> 
        </li>
        <li class="flex justify-center">
            <button on:click={(event) => handleClick(event, "drinks")} class="w-1/2 py-2 text-center font-semibold text-text-primary cursor-pointer hover:bg-primary-dark {drinkActive ? 'bg-primary-dark': 'bg-primary'}">Drinks</button> 
        </li>
    </ul>
    {#if isDataImported}    
        {#each menuList as l}
            <MenuList title={l.title} items={l.items}/>
        {/each}
    {/if}
</div>

<script>
    import MenuList from "./MenuList.svelte";
    import { onMount } from "svelte"; 
    import goatCurry from "$lib/assets/menus/dinner/goat-curry.jpg"

    const menudata = {    dinner: [
            {
                title: "For The Table",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry 
                    },
                    {
                        name: "Dinner Test2 dinner test dinner test",
                        description: "description",
                        src: goatCurry 
                    }
                ]
            },

            {
                title: "Dinner Title 2",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry 
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry 
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry 
                    }
                ]
            }
        ],
        lunch: [

            {
                title: "Lunch Title 1",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Lunch Test | $3.99",
                        description: "decription",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry
                    }
                ]
            },

            {
                title: "Lunch Title 2",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry
                    }
                ]
            }
        ],
        brunch: [

            {
                title: "Brunch Title 1",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry
                    }
                ]
            },

            {
                title: "Brunch Title 2",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry
                    }
                ]
            }
        ],
        drinks: [
 

            {
                title: "Drink Title 1",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry
                    }
                ]
            },

            {
                title: "Drink Title 2",
                items: [
                    {
                        name: "Goat Curry And Rice",
                        description: "This is goat curry and rice.",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test",
                        description: "decription",
                        src: goatCurry
                    },
                    {
                        name: "Dinner Test2",
                        description: "description",
                        src: goatCurry
                    }
                ]
            }
        ]
    }


    let originalData
    let menuList
    let isDataImported = false
    let dinnerActive = true
    let lunchActive = false
    let brunchActive = false
    let drinkActive = false

    function changeActiveToFalse() {
        dinnerActive = false
        lunchActive = false
        brunchActive = false
        drinkActive = false
    }

    onMount(() => {
      originalData = menudata
      menuList = originalData.dinner
      console.log(menuList)
      isDataImported = true
    })


    function handleClick(event, arg) {
        menuList = originalData[arg]
        
        if (arg === "dinner") {
            changeActiveToFalse()
            dinnerActive = true
        } else if (arg === "lunch") {
            changeActiveToFalse()
            lunchActive = true
        } else if (arg === "brunch") {
            changeActiveToFalse()
            brunchActive = true
        } else if (arg === "drinks") {
            changeActiveToFalse()
            drinkActive = true
        }
    }

</script>