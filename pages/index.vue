<template>
    <div>
        <main>
            
            <div class="container">
                <h1>Home page 23333333333</h1>

                <FormInput 
                    v-model:modelValue="phone" 
                    name="phone" 
                    type="text"
                    :label="$t('auth.phone_label')" 
                    :placeholder="$t('auth.phone_label')" 
                    :validation-schema="phoneNumber"
                />
                <FormInput 
                    v-model:modelValue="text" 
                    name="phone" 
                    type="text"
                    :label="$t('auth.phone_label')" 
                    :placeholder="$t('auth.phone_label')" 
                    :validation-schema="email"
                />
            </div>
    
        </main>
    </div>
</template>

<script setup>

definePageMeta({
    name: "Titles.home",
});

const phone = ref(null);
const text = ref(null);

const { phoneNumber, email } = useValidationSchema();

</script>
