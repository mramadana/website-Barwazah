<template>
    <section class="container">
        <h3 class="main-title mb-4 xl bold text-center">الأسئلة الشائعة</h3>
        <h4 class="main-title mb-5 md text-center">أكتشف المزيد حول خدمات بروزة وكيفية تحقيق أقصى استفادة منها</h4>
        <div class="row accordion accordion-flush justify-content-center mt-5" id="accordionFlushExample">
            <div class="col-12 col-md-10 mb-4" v-for="item in FAQ" :key="item.id">
                <div class="chart_layout">
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" :data-bs-target="'#flush-collapseOne' + item.id" aria-expanded="false" :aria-controls="'flush-collapseOne' + item.id">
                                <span>{{ item.question }}</span>
                            </button>
                        </h2>
                        <div :id="'flush-collapseOne' + item.id" class="accordion-collapse collapse" data-bs-parent="#accordionFlushExample">
                            <div class="accordion-body">
                                {{ item.answer }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>

const FAQ = ref([
    {
        id: 1,
        question: "ما هي بروزة وما الخدمات التي تقدمها؟",
        answer: "بروزة هي تطبيق ذكي للمساعدة التسويقية يقدم خدمات تحليل البيانات وتوليد المحتوى واقتراح استراتيجيات تسويقية مخصصة باستخدام الذكاء الاصطناعي"
    },
    {
        id: 2,
        question: "كيف يمكن للتطبيق أن يساعدني في تحسين استراتيجيات التسويق الخاصة بي؟",
        answer: "بروزة يمكن أن يساعدك في تحسين استراتيجيات التسويق من خلال تحليل بيانات العملاء وسلوكهم، وتقديم توصيات مخصصة لحملات التسويق، واقتراح محتوى مناسب لجمهورك المستهدف، وتحسين معدلات التحويل باستخدام تقنيات الذكاء الاصطناعي"
    },
    {
        id: 3,
        question: "ما الذي يميز أدوات التحليل في التطبيق مقارنة بالأدوات التحليلية الأخرى المتاحة؟",
        answer: "تتميز أدوات التحليل في بروزة بقدرتها على دمج البيانات من مصادر متعددة، وتقديم تحليلات متقدمة باستخدام الذكاء الاصطناعي، وتوفير رؤى قابلة للتنفيذ بشكل مباشر، مما يجعلها أكثر شمولية وفعالية من الأدوات التقليدية"
    },
    {
        id: 4,
        question: "هل يمكن استخدام التطبيق لأي نوع من المتاجر الإلكترونية (الصغيرة - المتوسطة - الكبيرة)؟",
        answer: "نعم، يمكن استخدام التطبيق لجميع أنواع المتاجر الإلكترونية، سواء كانت صغيرة أو متوسطة أو كبيرة الحجم. تم تصميم بروزة ليكون مرناً وقابلاً للتكيف مع احتياجات مختلف أحجام الأعمال التجارية"
    },
    {
        id: 5,
        question: "هل يمكنني استخدام التطبيق بغض النظر عن نوع المجال الذي أعمل فيه؟",
        answer: "نعم، يمكنك استخدام التطبيق بغض النظر عن نوع المجال الذي تعمل فيه. تم تصميم بروزة ليكون متعدد الاستخدامات ومناسباً لمختلف القطاعات والصناعات"
    },
    {
        id: 6,
        question: "هل يدعم التطبيق خططاً تسويقية مخصصة للسوق السعودي؟",
        answer: "نعم، يدعم التطبيق خططاً تسويقية مخصصة للسوق السعودي. يتم تصميم الاستراتيجيات والتوصيات بناءً على فهم عميق لخصائص وتفضيلات المستهلكين في المملكة العربية السعودية، مما يضمن فعالية الحملات التسويقية في السياق المحلي"
    },
    {
        id: 7,
        question: "هل يحتاج التطبيق إلى مهارات خاصة لاستخدامه؟",
        answer: "لا، تم تصميم التطبيق ليكون سهل الاستخدام وبديهي للمستخدمين بمختلف مستويات الخبرة. يوفر التطبيق واجهة مستخدم بسيطة وإرشادات واضحة لمساعدتك في استخدام جميع الميزات بفعالية."
    },
    {
        id: 8,
        question: "كيف يمكنني استخدام الذكاء الاصطناعي في التطبيق؟",
        answer: "يمكنك استخدام الذكاء الاصطناعي في التطبيق من خلال عدة طرق، مثل تحليل البيانات، وتوليد المحتوى، واقتراح استراتيجيات تسويقية مخصصة. يقدم التطبيق أدوات ذكية تعتمد على الذكاء الاصطناعي لتحسين قراراتك التسويقية وتعزيز فعالية حملاتك."
    },
    {
        id: 9,
        question: "ما الفرق بين المساعد التسويقي \"بروزة\" وثابت أنظمة الذكاء الاصطناعي الأخرى؟",
        answer: "يتميز \"بروزة\" بتركيزه الخاص على التسويق الرقمي والتجارة الإلكترونية، مع تخصيص للسوق السعودي. يوفر حلولاً شاملة ومتكاملة تجمع بين تحليل البيانات وتوليد المحتوى واقتراح الاستراتيجيات، مما يجعله أكثر تخصصًا وفعالية للمسوقين مقارنة بأنظمة الذكاء الاصطناعي العامة."
    },
    {
        id: 10,
        question: "هل يتم تحديث التطبيق بشكل دوري لإضافة مميزات جديدة؟",
        answer: "نعم، يتم تحديث التطبيق بشكل دوري لإضافة ميزات جديدة وتحسين الأداء. نحن نستمع باستمرار لملاحظات المستخدمين ونراقب اتجاهات السوق لضمان بقاء التطبيق في طليعة التكنولوجيا التسويقية."
    },
    {
        id: 11,
        question: "هل بإمكاني أمان عند استخدام التطبيق؟",
        answer: "نعم، نحن نأخذ أمن وخصوصية بياناتك على محمل الجد. يستخدم التطبيق تقنيات تشفير متقدمة وإجراءات أمنية صارمة لحماية معلوماتك. نلتزم أيضًا بجميع قوانين حماية البيانات المعمول بها لضمان استخدام آمن وموثوق."
    },
    {
        id: 12,
        question: "هل يوجد فريق دعم يمكنني التواصل معه؟",
        answer: "نعم، لدينا فريق دعم متخصص ومتاح للمساعدة في أي استفسارات أو مشكلات قد تواجهها. يمكنك التواصل معنا عبر البريد الإلكتروني، الدردشة المباشرة، أو الهاتف خلال ساعات العمل المحددة. نحن ملتزمون بتقديم تجربة دعم استثنائية لجميع مستخدمينا."
    }
]);

</script>

<style lang="scss">
.accordFaq {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(500px, 1fr));
    gap: 15px;
    margin-bottom: 15px;
    font-family: 'main_font' !important;
    font-size: 14px !important;
}

.accordion-button {
    background-color: #fff;
    border: none;
    color: var(--red);
    padding: 20px;
    @media (max-width: 550px) {
        padding: 15px;
    }
    &:focus {
        box-shadow: none;
    }
}

.accordion-item {
    border: none;
    box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.10);
    border-radius: 15px !important;
    overflow: hidden;
    &:not(:last-child) {
        margin-bottom: 15px;
    }
}

.accordion-button::after {
    transform: rotate(0deg);
    content: "\f067";
    font-size: 15px;
    font-weight: 600;
    background-image: none !important;
    color: #E5254A;
}

.accordion-button:not(.collapsed)::after {
    transform: rotate(45deg);
}

.accordion-button:not(.collapsed) {
    background-color: rgba(238, 246, 254, 1);
    color: var(--red);
}

.layout-Faq {
    background-color: var(--wh);
    box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.10);
    border-radius: 10px;
    margin-bottom: 30px;
    padding: 18px;
}

@media (max-width: 550px) {
    .accordFaq {
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    }
    .accordion-button {
        font-size: 13px;
    }
}
</style>