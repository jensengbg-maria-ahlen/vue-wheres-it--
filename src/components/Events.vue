<template>
<section>
        <li>
            <h5 v-on:click="addTicket">{{eventData.when.date}}</h5>
            <section>
                <h4 v-on:click="addTicket">{{eventData.what}}</h4>
                <h3 v-on:click="addTicket">{{eventData.where.venue}}</h3>
                <h2 v-on:click="addTicket">{{eventData.when.from + ' - ' + eventData.when.to}}</h2>
            </section>
            <h6 v-on:click="addTicket">{{eventData.price + ' sek'}}</h6>
        </li>
</section>
</template>

<script>
export default {
    name: 'all-events',
    props: {
        eventData: Object
    },
    methods: {
        async getEvents() {
            const response = await fetch("events.json");
            const data = await response.json();
            this.events = data;
        },
        addTicket() {
            this.$parent.tickets.push(JSON.stringify(this.eventdata));
            console.log(JSON.stringify(this.eventData));
        }
    }

}
</script>

<style lang="scss">

    li {
        margin: 1rem;
        display: flex;
        align-items: center;
        color: white;

        section {
            display: flex;
            flex-direction: column;
            margin-right: 1rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.3);
        }


        h5 {
            display: flex;
            justify-content: center;
            border: 1px solid white;
            border-radius: 10%;
            width: 66px;
            height: 66px;
            font-family: Fira Sans;
            font-style: normal;
            font-weight: bold;
            font-size: 14px;
            align-items: center;
            text-align: center;
            margin: 1rem;
        }


        h4 {
            width: 202px;
            height: 30px;
            font-family: Fira Sans;
            font-style: normal;
            font-weight: 600;
            font-size: 22px;
            line-height: 26px;
            display: flex;
            align-items: center;
            color: #FFFFFF;
            text-shadow: 1px 1px 0px #F56B9A;
        }

        h3 {
           font-family: Fira Sans;
            font-style: italic;
            font-weight: normal;
            font-size: 12px;
            line-height: 14px;
            color: rgba(255, 255, 255, 0.8);
        }

        h2 {
            font-family: Fira Sans;
            font-style: normal;
            font-weight: 600;
            font-size: 14px;
            line-height: 17px;
            color: #D0D0D0;  
        }

        h6 {
            width: 109px;
            height: 27px;
            font-family: Fira Sans;
            font-style: normal;
            font-weight: bold;
            font-size: 17px;
            line-height: 20px;
            display: flex;
            align-items: flex-end;
            text-align: right;
            color: #37AEAB; 
        }
    }

</style>