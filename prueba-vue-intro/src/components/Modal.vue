    <template>
        <div class="backdrop" @click="click('normal click')" @click.self="exitModal()">
            <aside class="modal-container">
                <h1 :class="titleClass">{{ title }}</h1>
                <slot><p>Not found</p></slot>

                <button @click="exitModal">x</button>
                <slot name="links"></slot>
            </aside>
        </div>
    </template>

    <script>
        export default {
            props: {
                title: String,
                titleColor: String
            },
            methods: {
                click(message){
                    console.log(message);
                },

                exitModal(){
                    this.$emit('close');
                }
            },
            computed: {
                titleClass() {
                    return `title--${this.titleColor}`
                }
            }
        }
    </script>

    <style scoped lang="scss">
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

        .title--red {
            color: red;
        }

        .title--blue{
            color: blue;
        }

        .modal-container{
            background-color: white;
            padding: 40px 20px;
        }
    </style>