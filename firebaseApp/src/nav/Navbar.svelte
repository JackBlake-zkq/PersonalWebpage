<script>
    import NavItem from './NavItem.svelte';

    function consumeEvent(evt){
        if (typeof evt.stopPropagation != "undefined") {
            evt.stopPropagation();
        } else {
            evt.cancelBubble = true;
        }
    }
</script>

<nav on:mousemove={consumeEvent}>
    <div>

        <NavItem label={'Home'} route={'/'} i={0}/>
        <NavItem label={'About'} route={'/about'} i={1}/>
        <NavItem label={'Contact'} route={'/contact'} i={2}/>
        <!-- <NavItem label={'Portfolio'} route={'/portfolio'} i={3}/> -->

    </div>
</nav>

<style>
    nav {
        position: fixed;
        background: var(--dark);
        width: 100%;
        z-index: 100;
    }
    div {
        float: right;
        display: flex;
        background-color: var(--light);
        background-image: var(--rainbow-grad);
        background-clip: text;
        -webkit-background-clip: text;
        -moz-background-clip: text;
    }
</style>