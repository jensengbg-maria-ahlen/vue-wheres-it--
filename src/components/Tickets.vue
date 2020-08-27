<template>
    <li class="ticketinfo">
        <div>
            <p>WHAT</p>
            <h2>{{ticketData.what}}</h2>
        </div>
        <div>
            <p>WHERE</p>
            <h2>{{ticketData.where.venue + ticketData.where.adress}}</h2>
        </div>
        <section>
            <div>
                <p>WHEN</p>
                <h2>{{ticketData.when.date}}</h2>
            </div>
            <div>
                <p>FROM</p>
                <h2>{{ticketData.when.from}}</h2>
            </div>
            <div>    
                <p>TO</p>
                <h2>{{ticketData.when.to}}</h2>
            </div>
        </section>
        <div>
            <p>INFO</p>
            <h2>{{ticketData.info}}</h2>
        </div>
        <div>
            <p>{{ticketData.ticketID}}</p>
        </div>
    </li>
</template>

<script>
export default {
    name: 'all-tickets',
    props: {
        ticketData: Object
    },
    methods: {
        async getTickets() {
            const response = await fetch("events.json");
            const data = await response.json();
            this.tickets = data;
        }
    }
}
</script>

<style lang="scss">

    .ticketinfo {
        margin: 1rem;
        display: flex;
        align-items: center;
        color: white;
        width: 300px;
        height: 550px;
        background: #FFFFFF;
        box-shadow: 0px 0px 32px rgba(0, 0, 0, 0.34);
        border-radius: 3px;
        display: flex;
        align-items: center;
        justify-content: space-between;

        div {
            font-family: Fira Sans;
            font-style: normal;
            font-weight: bold;
            font-size: 12px;
            line-height: 12px;
            display: flex;
            align-items: center;
            color: rgba(0, 0, 0, 0.4);
        }
        
    }

</style>