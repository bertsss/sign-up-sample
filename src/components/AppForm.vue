<template>
    <div class="form-container">
        <h1>Lorem ipsum dolor sit amet</h1>

        <p class="desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed.<br/> tempor incididunt ut labore et dolore magna aliqua.
        </p>

        <form @submit.prevent="submit()">
            <div class="field-wrapper">
                <p class="label">Company Name</p>
                <input type="text">
            </div>
    
            <div class="two-field">
                <div class="field-wrapper">
                    <p class="label">First Name*</p>
                    <input type="text">
                </div>
    
                <div class="field-wrapper">
                <p class="label">Last Name*</p>
                    <input type="text">
                </div>
            </div>
    
            <div class="field-wrapper">
                <p class="label">Telephone*</p>
                <input type="text" class="telephone">

                <div class="option-wrapper">
                    <div class="selected" @click="viewOpt = !viewOpt">NL +31</div>
                    <i class="fa fa-chevron-down down" aria-hidden="true" @click="viewOpt = !viewOpt"></i>
                
                    <div class="options" v-if="viewOpt">
                        <p>PH +63</p>
                    </div>
                </div>
            </div>
    
            <div class="field-wrapper">
                <p class="label">Email Address (Business)*</p>
                <input type="email" class="error">
                <i class="fa fa-exclamation-circle ex" aria-hidden="true"></i>
            </div>
    
            <div class="two-field">
                <div class="field-wrapper">
                    <p class="label">Password*</p>
                    <input :type="pwType">
                    <i class="fa fa-eye" v-if="pwType === 'password'" @click="pwType='text'"></i>
                    <i class="fa fa-eye-slash" v-else @click="pwType='password'"></i>
                    <div class="length-wrapper">
                        <div class="pw-meter weak"></div>
                        <div class="pw-meter medium"></div>
                        <div class="pw-meter long"></div>
                    </div>
                </div>
    
                <div class="field-wrapper">
                <p class="label">Confirm Password*</p>
                    <input :type="cpwType">
                    <i class="fa fa-eye" v-if="cpwType === 'password'" @click="cpwType='text'"></i>
                    <i class="fa fa-eye-slash" v-else @click="cpwType='password'"></i>
                </div>
            </div>
    
            <div class="terms">
                <input type="checkbox" class="checkbox">
                I agree with the
                <a href="sampletermsandconditions/link" target="_blank">
                    Terms and Conditions
                </a>
            </div>
    
            <div class="button-wrapper">
                <button type="submit">Create a Free Account</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data () {
        return {
            pwType: 'password',
            cpwType: 'password',
            viewOpt: false
        }
    },
    
    methods: {
        submit () {
            console.log('submit')
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/assets/styles/variables";

.form-container {
    border-radius: 20px;
    border: 1px solid #b3b4b5;
    padding: 30px 20px;

    h1 {
        margin-bottom: 15px;
    }

    .desc {
        font-weight: 400;
        padding-bottom: 20px;
        border-bottom: 1px solid #b3b4b5;
        color: #636262;
        margin-bottom: 20px;
        font-size: 16px;
    }

    .field-wrapper {
        display: flex;
        flex-direction: column;
        margin-bottom: 15px;
        position: relative;

        .label {
            margin-bottom: 8px;
            font-size: 12px;
            font-weight: 400;
        }

        input {
            border-radius: 5px;
            outline: none;
            box-shadow: none;
            border: 1px solid $gray;
            padding: 8px;
            font-size: 12px;

            &.error {
                border-color: red;
            }

            &.telephone {
                padding-left: 95px;
            }
        }

        i {
            position: absolute;
            height: 12px;
            width: 12px;
            right: 12px;
            top: 31px;
            cursor: pointer;

            &.ex {
                color: red;
            }
        }

        .option-wrapper {
            position: absolute;
            left: 15px;
            top: 30px;
            width: 70px;
            display: flex;
            align-items: center;

            .selected {
                margin-right: 10px;
                cursor: pointer;
            }

            .down {
                position: unset;
                font-size: 10px;
            }

            .options {
                position: absolute;
                border: 1px solid $gray;
                border-radius: 5px;
                background-color: $white;
                padding: 5px 10px;
                top: 28px;
                left: -15px;
                z-index: 2;
                cursor: pointer;
                width: 70px;
            }
        }

        .length-wrapper {
            display: flex;
            justify-content: space-between;
            margin-top: 8px;

            .pw-meter {
                height: 2px;
                background-color: #d6d6d6;
                width: 32%;

                &.weak {
                    background-color: #fa534d;
                }

                &.medium {
                    background-color: #faa94d;
                }

                &.long {
                    background-color: #4dfa53;
                }
            }
        }
    }

    .two-field {
        display: flex;
        justify-content: space-between;

        > * {
            width: 49%;
        }
    }
    
    .terms {
        margin: 10px 0 20px;

        .checkbox {
            margin-right: 8px;
        }

        a {
            color: $blue;
        }
    }

    .button-wrapper {
        display: flex;

        button {
            outline: none;
            cursor: pointer;
            border: 1px solid $blue;
            background-color: $blue;
            color: $white;
    
            border-radius: 20px;
            padding: 8px 12px;
    
            margin-left: auto;
        }
    }

}
</style>