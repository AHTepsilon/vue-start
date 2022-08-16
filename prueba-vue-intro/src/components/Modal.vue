    <template>
        <div class="backdrop" @click="click('normal click')" @click.self="exitModal()">
            <aside class="modal-container">
                <h1>Hello, I'm a modal</h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui nihil ab minus. Ipsum porro earum iusto vel culpa, quam similique nemo id ab, officia, maxime eaque sapiente odit distinctio dignissimos!</p>

                <button @click="exitModal">x</button>
            </aside>
        </div>
    </template>

    <script>
        export default {
            methods: {
                click(message){
                    console.log(message);
                },

                exitModal(){
                    this.$emit('close');
                }
            }
        }
    </script>

    <style>
        .backdrop{
            background-color: rgba(0, 0, 0, 0.5);
            width: 100%;
            height: 100%;
            position: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
            top: 0;
            bottom: 0;
            left: 0;
        }

        .modal-container{
            background-color: white;
            padding: 40px 20px;
        }
    </style>