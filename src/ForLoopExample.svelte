<script>
    let people =[
        {name:'Test name ', beltColor: 'red', age:20, id:1}, 
        {name:'Timma ', beltColor: 'yellow', age:20, id:2}, 
        {name:'Priya ', beltColor: 'black', age:20, id:3}
    ]

    const handleClick = (id) =>{
            people = people.filter((person) => person.id !=id)
    }
    let n = 5
</script>


<style>
    main{
        text-align: center;
    }
</style>
<main>
    {#each people as p}
        <div>
            <h4>{p.name}</h4>
            {#if p.beltColor === 'black'}
                <p><strong>MASTERNINJA</strong></p>
            {/if}
            <p>{p.age} years old, {p.beltColor} belt</p>
            <button on:click={() => {handleClick(p.id)}}>Delete</button>
        </div>
        {:else}
            <p> There are no person to show</p>
    {/each}

    {#if n > 20}
    <p> number is greater than 20</p>
    {:else if n < 5}
        <p> Number is less than 5</p>
    {:else}
        <p> Not greater than 5</p>
    {/if}
</main>