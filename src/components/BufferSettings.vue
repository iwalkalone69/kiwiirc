<template>
    <div class="kiwi-buffersettings">
        <div class="kiwi-buffersettings-alerts">
            <form class="u-form">
                <b>{{$t('settings_notify')}}: </b><br />
                <label>
                    <input type="radio" name="alert_on" value="message" v-model="settingAlertOn">
                    <span>{{$t('settings_notify_all')}}</span>
                </label><br />
                <label>
                    <input type="radio" name="alert_on" value="highlight" v-model="settingAlertOn">
                    <span>{{$t('settings_notify_mentioned')}}</span>
                </label><br />
                <label>
                    <input type="radio" name="alert_on" value="never" v-model="settingAlertOn">
                    <span>{{$t('settings_notify_never')}}</span>
                </label><br />

                <label>
                    <input type="checkbox" v-model="settingMuteSound">
                    <span>{{$t('settings_notify_mute')}}</span>
                </label><br />
            </form>
        </div>
    </div>
</template>

<script>

export default {
    data: function data() {
        return {
        };
    },
    props: ['buffer'],
    components: {
    },
    computed: {
        settingAlertOn: {
            get: function getSettingAlertOn() {
                return this.buffer.setting('alert_on');
            },
            set: function setSettingAlertOn(val) {
                return this.buffer.setting('alert_on', val);
            },
        },
        settingMuteSound: {
            get: function getSettingAlertOn() {
                return this.buffer.setting('mute_sound');
            },
            set: function setSettingAlertOn(val) {
                return this.buffer.setting('mute_sound', val);
            },
        },
    },
};
</script>

<style>

.kiwi-buffersettings {
    box-sizing: border-box;
}
.kiwi-buffersettings-alerts {
    margin-bottom: 1em;
}

</style>
