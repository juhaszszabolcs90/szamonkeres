<script>
    const { data } = $props()
    let urlap = $state(0)
</script>

<h1>Eszközök ({data.user?.username})</h1>

{#if urlap === 0}
<button class="ui green small button" onclick={() => urlap=1}>Új eszköz</button>
{/if}
{#if urlap === 1}
<button class="ui blue small button" onclick={() => urlap=0}>Űrlap bezárása (mentés nélkül)</button>
    <form action="?/ujeszkoz" method="POST">
        <div class="ui input">
            <div class="ui label">Szöveg</div>
            <input type="text" name="title" />
        </div>
        <div class="ui input">
            <div class="ui label">Leírás</div>
            <input type="text" name="description" />
        </div>
        <div class="ui input">
            <div class="ui label">Kepek</div>
            <input type="text" name="image" />
        </div>
        <div class="ui input">
            <div class="ui label">Számítószám</div>
            <input type="text" name="number" />
        </div>
        <div class="ui input">
            <div class="ui label">Felhasználó</div>
            <input type="text" name="user" />
        </div>
        <button class="ui green small button">Mentés</button>
    </form>
{/if}