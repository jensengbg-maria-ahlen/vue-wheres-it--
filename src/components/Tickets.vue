<template>
    <li class="ticketinfo">
        <div class="what">
            <p>WHAT</p>
            <h2>{{eventData.what}}</h2>
        </div>
        <div class="where">
            <p>WHERE</p>
            <h2>{{eventData.where.venue}}</h2>
            <h3>{{eventData.where.adress}}</h3>
        </div>
        <section class="date">
            <div class="when">
                <p>WHEN</p>
                <h2>{{eventData.when.date}}</h2>
            </div>
            <div class="from">
                <p>FROM</p>
                <h2>{{eventData.when.from}}</h2>
            </div>
            <div class="to">    
                <p>TO</p>
                <h2>{{eventData.when.to}}</h2>
            </div>
        </section>
        <div class="info">
            <p>INFO</p>
            <h3>{{eventData.info}}</h3>
        </div>
        <div class="id">
            <img src="../assets/A2ED7barcode.png" alt="barcode">
            <p>{{eventData.ticketID}}</p>
        </div>
    </li>
</template>

<script>
export default {
    name: 'all-tickets',
    props: {
        eventData: Object
    }
}
</script>

<style lang="scss">

    .ticketinfo {
        margin: 1rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        color: white;
        width: 300px;
        height: 450px;
        background: #FFFFFF;
        box-shadow: 0px 0px 32px rgba(0, 0, 0, 0.34);
        border-radius: 3px;

        div {
            font-family: Fira Sans;
            font-style: normal;
            font-weight: bold;
            font-size: 12px;
            line-height: 12px;
            display: flex;
            flex-direction: row;
            align-items: center;
            color: rgba(0, 0, 0, 0.4);
        }

        .what {
            width: 300px;
            height: 80px;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            justify-content: flex-start;

            p {
                margin-left: 1rem;
            }

            h2 {
                font-family: Sansita;
                font-style: italic;
                font-weight: bold;
                font-size: 26px;
                line-height: 30px;
                display: flex;
                align-items: center;
                color: #F56B9A;
                margin-left: 1rem;
            }
        }

        .where {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            justify-content: flex-start;
            width: 300px;
            height: 120px;
            background: rgba(0, 0, 0, 0.03);
            border-top: 1px dashed rgba(0, 0, 0, 0.4);

            p {
                margin-left: 1rem;
            }

            h2 {
                font-family: Fira Sans;
                font-style: normal;
                font-weight: bolder;
                font-size: 18px;
                line-height: 22px;
                display: flex;
                align-items: center;
                color: rgba(0, 0, 0, 0.7);
                margin-left: 1rem;
            }

            h3 {
                font-family: Fira Sans;
                font-style: normal;
                font-weight: bolder;
                font-size: 10px;
                line-height: 22px;
                display: flex;
                align-items: center;
                color: rgba(0, 0, 0, 0.7);
                margin-left: 1rem;
            }
        }

        .date {
            color: rgba(0, 0, 0, 0.6);
            display: flex;
            flex-direction: row;

            .when, .from, .to {
                width: 98px;
                height: 60px;
                display: flex;
                flex-direction: column;
                border: 1px dashed rgba(0, 0, 0, 0.4);
                padding: 0;

                p {
                margin-top: 0.5rem;
                margin-left: -3rem;
                }

                h2 {
                    font-family: Fira Sans;
                    font-style: normal;
                    font-weight: bolder;
                    font-size: 18px;
                    margin-left: -1.5rem;
                    color: rgba(0, 0, 0, 0.6);
                }
            }
        }

        .info {
            background: rgba(168, 168, 168, 0.12);
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            align-items: flex-start;
            width: 300px;
            height: 80px;
            padding-top: .5rem;

            p {
                margin-left: 1rem;
            }

            h3 {
                font-family: Fira Sans;
                font-style: normal;
                font-weight: bolder;
                font-size: 10px;
                line-height: 22px;
                display: flex;
                align-items: center;
                color: rgba(0, 0, 0, 0.7);
                margin-left: 1rem;
            }

        }

        .id {
            width: 300px;
            height: 200px;
            background: rgba(0, 0, 0, 0.12);
            border-radius: 0px 0px 3px 3px;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            align-items: center;
            font-family: Fira Sans;
            font-style: normal;
            font-weight: bolder;
            font-size: 15px;
            line-height: 14px;
            color: rgba(0, 0, 0, 0.4);
            padding-bottom: 2rem;
        }


    }

</style>