<template> 
  <main id="app">
    <section >
      <h1>Events</h1>
      <ul>
        <all-events 
        v-for="(event, index) in events"
        v-bind:key="index"
        v-bind:eventData="event" 
        />
      </ul>
    </section>
    
    <section id="tickets">
      <h1>Tickets</h1>
      <ul>
        <all-tickets 
        v-for="(ticket, index) in tickets"
        v-bind:key="index"
        v-bind:eventData="ticket"
        />
      </ul>
    </section>
    
  </main>
</template>

<script>
  import { data, tickets} from './events.json';
  import AllEvents from './components/Events';
  import AllTickets from './components/Tickets';

export default {
  name: 'EventApp',
  components: {
    AllEvents,
    AllTickets
  },
  data(){
    return {
      events: data,
      tickets: tickets
    }
  }

}
</script>

<style lang="scss">

*, html {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    height: 1000vh;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    background-color: #231F42;

    #app {
      width: 200vw;
      min-width: 1000px;
      display: flex;
      justify-content: center;

      h1 {
        margin-left: 2rem;
        font-family: Sansita;
        color: #F56B9A;
        font-weight: bold;
        font-size: 32px;
        line-height: 37px;
      }

      #tickets {
        display: flex;
        flex-direction: column;
      }
    }
  }

</style>