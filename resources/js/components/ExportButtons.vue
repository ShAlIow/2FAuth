<script setup>
    import { UseColorMode  } from '@vueuse/components'

    const router = useRouter()
    const emit = defineEmits(['export-twofauth-format', 'export-otpauth-format'])
    const $2fauth = inject('2fauth')

</script>

<template>
    <div class="block">
        <UseColorMode v-slot="{ mode }">
            <p class="has-text-weight-bold has-text-grey">
                {{ $t('twofaccounts.twofauth_export_format_sub') }}
            </p>
        </UseColorMode>
        <p class="is-size-7-mobile">
            {{ $t('twofaccounts.twofauth_export_format_desc') }}
            {{ $t('twofaccounts.twofauth_export_format_url') }}
            <a id="lnkExportSchemaUrl" class="is-link" tabindex="0" :href="$2fauth.urls.exportSchemaUrl" target="_blank">
                {{ $t('twofaccounts.twofauth_export_schema') }}
            </a>
        </p>
        <button type="button" id="btnExport2FAuth" class="button is-link is-rounded is-focus my-3" @click="$emit('export-twofauth-format')" :title="$t('twofaccounts.twofauth_export_format_sub')">
            {{ $t('twofaccounts.twofauth_export_format') }}
        </button>
    </div>
    <div class="block">
        <p class="has-text-weight-bold has-text-grey">
            {{ $t('twofaccounts.otpauth_export_format_sub') }}
        </p>
        <p class="is-size-7-mobile">
            {{ $t('twofaccounts.otpauth_export_format_desc') }}
        </p>
        <button type="button" id="btnExportOtpauth" class="button is-link is-rounded is-focus my-3" @click="$emit('export-otpauth-format')" :title="$t('twofaccounts.otpauth_export_format_sub')">
            {{ $t('twofaccounts.otpauth_export_format') }}
        </button>
    </div>
</template>