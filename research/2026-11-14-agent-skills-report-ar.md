# تقرير بحث GitHub: مهارات صناعة المحتوى والفيديو والصوت والتصميم
**تاريخ الفحص:** 14 نوفمبر 2026  
**النتيجة:** 16 ملف Agent Skill فعلي تم فتحه والتحقق من محتواه، ونسخه إلى هذا المستودع في مجلد `skills/upstream/`، مع حفظ تراخيص المصدر المتاحة في `licenses/upstream/`.

> هذا أرشيف لملفات `SKILL.md` الأصلية وليس تثبيتاً للمهارات داخل ChatGPT. لم أنفّذ أي تحرير أو توليد أو نشر لوسائط. لم أنسخ سكربتات/مراجع/نماذج المهارات الخارجية؛ قد تحتاج بعض المهارات إلى استنساخ مستودعها الأصلي حتى تعمل كل المسارات المذكورة في ملفها.

## الملخص التنفيذي

أقوى ما ظهر في البحث هو أربع مجموعات عملية:
1. **تحرير فيديو قابل للتحقق:** FFmpeg Skill وTyped Video Editing وVideo Editing Workbench، مع dry-run وعقود إدخال ومخرجات وقياس/checksums/provenance.
2. **تحويل الفيديو إلى محتوى منشور:** Talking-head editing وVideo-to-Shorts وYouTube publishing، وتشمل transcription وcut lists وcaptions وchapters وapproval قبل النشر.
3. **الإنتاج الإبداعي المتخصص:** Gemini Omni لتوليد/تعديل الفيديو عبر API، After Effects expressions/export/project hygiene، وBlender 5.3 animation/mocap/retargeting وprevis/storyboards.
4. **الصوت والترجمة النصية:** Caption Styling وAudio Ducking، وهما تعليمات عامة قابلة للتطبيق في عدة برامج مع سكربتات بسيطة.

## النتائج المرتبة حسب الفائدة العملية

### 1) FFmpeg Skill — تحرير فيديو وصوت محلي واسع النطاق
- **ما تنفذه:** قص، دمج، إعادة تأطير، تغيير سرعة، captions/overlays، إزالة صمت، مزامنة، loudness، HDR-to-SDR، فحص وتصدير حسب منصة. توفر 42 أداة بحسب وصف المهارة، مع عقد لكل أداة وdry-run وJSON.
- **ملف المهارة:** [SKILL.md](https://github.com/kajisho5/ffmpeg-skill/blob/main/SKILL.md) — محلياً: `skills/upstream/ffmpeg-skill/SKILL.md`.
- **آخر تغيير لملف المهارة:** [commit 18aa240](https://github.com/kajisho5/ffmpeg-skill/commit/18aa2402c887c927e59169fc2946b9dc5b3e1545)، 2026-11-14 13:53 UTC. آخر إصدار ظاهر في المستودع: 3.8.14 في اليوم نفسه.
- **الترخيص:** MIT، تم التحقق من LICENSE وحفظه.
- **التشغيل والمتطلبات:** CLI محلي؛ FFmpeg 6.1+ وPython 3.10+، مكتبات Python القياسية فقط، بلا خدمة سحابية أو مفتاح API وفق frontmatter.
- **ChatGPT:** يمكن استخدام التعليمات لتخطيط الأوامر وفحصها، لكن التنفيذ يتطلب بيئة محلية فيها FFmpeg والملفات؛ لا يعمل داخل المحادثة تلقائياً.
- **التقييم:** مرتفع جداً. مناسب كأساس تحرير إنتاجي قابل للتدقيق. لا يتخذ قرارات المونتاج الفنية نيابة عن المحرر؛ يجب اختيار التعديلات أولاً.  
- **المستودع:** https://github.com/kajisho5/ffmpeg-skill

### 2) Typed Video Editing — تنفيذ تعديل فيديو بعقد typed دون أوامر حرة
- **ما تنفذه:** TRIM/CUT/CONCAT/TRANSITION/SPEED/FIT/FILL/RESIZE/OVERLAY/ROTATE/FREEZE/REVERSE/IMAGE_INSERT/CROP/CONDENSE/PUNCH_IN. يحول طلب تعديل منظم إلى خطوات، ويراقب خريطة المصدر إلى timeline، ويعيد provenance وSHA-256 ونتائج probe.
- **ملف المهارة:** [SKILL.md](https://github.com/kajisho5/video-editing-skill/blob/main/SKILL.md) — محلياً: `skills/upstream/typed-video-editing/SKILL.md`.
- **آخر تغيير:** [commit 5134734](https://github.com/kajisho5/video-editing-skill/commit/5134734adbb9f2dc6123548d523aea6bf6cb9189)، 2026-11-13 17:31 UTC؛ الإصدار 0.8.0.
- **الترخيص:** MIT، محفوظ.
- **المتطلبات:** Python 3.9+ بلا حزم إضافية؛ يتطلب checkout من ffmpeg-skill بإصدار 0.10.0+ ووجود ffmpeg/ffprobe في PATH. الأمر الأساسي `video-editing run`، مع `doctor` و`plan` و`contract`.
- **ChatGPT:** مناسب كتعليمات وكعقد typed؛ التنفيذ يحتاج CLI ونظام ملفات وffmpeg-skill مثبتاً. لا يقبل أوامر/argv/filter strings حرة؛ هذا حد أمان مقصود.
- **التقييم:** مرتفع جداً عندما تكون قرارات القص قد اتخذت مسبقاً. ليس نظام اختيار لقطات ولا تصحيح ألوان ولا mastering صوتي.
- **المستودع:** https://github.com/kajisho5/video-editing-skill

### 3) Video Editing Workbench — ورشة تحرير ومراجعة نهائية
- **ما تنفذه:** فحص مصادر حقيقي، transcription عند الحاجة، تخطيط timeline وtracks، توليد draft منخفض الدقة وcontact sheets وtransition strips وstills، ثم رندر FFmpeg أو Remotion والتحقق من الملف النهائي.
- **ملف المهارة:** [SKILL.md](https://github.com/gitethanwoo/video-editing/blob/main/skills/video-editing/SKILL.md) — محلياً: `skills/upstream/video-editing-workbench/SKILL.md`.
- **آخر تغيير موثق للمهارة:** [commit 166eed9](https://github.com/gitethanwoo/video-editing/commit/166eed9b1f391af5201a37057924593bf8f413d4)، 2026-07-29؛ المستودع نفسه شهد لاحقاً commit في 2026-11-12 لنقل مهارات فيديو أخرى داخله، وليس دليلاً على تغيير هذا الملف.
- **الترخيص:** MIT للمستودع، تم التحقق منه وحفظه.
- **المتطلبات:** Python وFFmpeg؛ مسار motion graphics يستخدم React/Remotion وNode/npm. توجد scripts ومراجع داخل المستودع الأصلي.
- **ChatGPT:** تعليماته قابلة للتكييف؛ أوامر render والملفات تتطلب بيئة محلية. Remotion يتطلب مشروع Node.
- **التقييم:** مرتفع جداً لسير عمل احترافي مع QC. لا يفرض أسلوباً بصرياً جاهزاً، وهذه ميزة.  
- **المستودع:** https://github.com/gitethanwoo/video-editing

### 4) Video to Shorts — تحويل فيديو طويل إلى Shorts/Reels/TikTok
- **ما تنفذه:** transcription مع word timestamps، اقتراح 8–12 لحظة، تقييم hook/standalone/payoff، إنشاء مقاطع 1080×1920، قص الصمت، إبقاء المتحدث داخل الإطار، captions كلمة بكلمة، عناوين ونصوص، ثم نشر اختياري بعد موافقة واضحة.
- **ملف المهارة:** [SKILL.md](https://github.com/social-media-skills/video-to-shorts-skill/blob/main/skills/video-to-shorts-skill/SKILL.md) — محلياً: `skills/upstream/video-to-shorts/SKILL.md`.
- **آخر تغيير:** [commit b5f3c40](https://github.com/social-media-skills/video-to-shorts-skill/commit/b5f3c4087791be00fc9740d3b507c82719e3d295)، 2026-10-29؛ الإصدار 1.0.0.
- **الترخيص:** MIT، محفوظ.
- **المتطلبات:** FFmpeg وPillow؛ transcription محلي عبر faster-whisper أو Groq/OpenAI API بمفتاح خاص. Groq موضح بنحو 0.04 دولار/ساعة صوت تقريباً؛ المحلي مجاني لكنه أبطأ. النشر يتطلب WoopSocial وربط الحسابات؛ لا توجد حاجة لمفتاح API إذا استُخدم المسار المحلي.
- **ChatGPT:** تخطيط وتقييم المرشحين ممكن؛ الرندر والرفع الفعلي يحتاجان CLI وملفات وتكامل WoopSocial. لا ينشر دون موافقة المستخدم.
- **التقييم:** مرتفع جداً لإعادة توظيف المحتوى. جودة الاختيار تعتمد على transcript ومراجعة الإنسان؛ حدود الطول/المنصة وسياسات حقوق المحتوى يجب مراجعتها.
- **المستودع:** https://github.com/social-media-skills/video-to-shorts-skill

### 5) Talking-head Video Editing — مونتاج المتحدث والكاميرا
- **ما تنفذه:** إزالة pauses وfillers والتأتأة والـ retakes وفق cut list قابلة للمراجعة، punch-ins، تنظيف/تسوية الصوت إلى -14 LUFS، SRT، YouTube chapters، وخيار vertical version أو النشر بعد الموافقة.
- **ملف المهارة:** [SKILL.md](https://github.com/social-media-skills/video-editing-skill/blob/main/skills/video-editing-skill/SKILL.md) — محلياً: `skills/upstream/talking-head-editing/SKILL.md`.
- **آخر تغيير:** [commit 4ba4092](https://github.com/social-media-skills/video-editing-skill/commit/4ba4092ab946a991d84087e2aa1408dc2c3e1cb2)، 2026-11-11. التغيير نقل تهيئة النشر إلى بداية workflow لتتم أثناء الرندر، وإصلاح دعم الحسابات الجديدة.
- **الترخيص:** MIT، محفوظ.
- **المتطلبات:** FFmpeg وPillow؛ faster-whisper محلي أو مفتاح GROQ_API_KEY/OPENAI_API_KEY؛ يدعم SRT/VTT موجوداً. النشر عبر WoopSocial ويتطلب ربط الحسابات.
- **ChatGPT:** مهارة عملية قوية للتخطيط والـ QA، لكن التنفيذ الفعلي CLI. يلزم تأكيد المستخدم قبل النشر.
- **التقييم:** مرتفع. مهم جداً الحفاظ على المعنى: المهارة تؤكد حماية كلمات المستخدم وعدم حذف ما تم تحديده keep.  
- **المستودع:** https://github.com/social-media-skills/video-editing-skill

### 6) Gemini Omni Flash — توليد وتعديل الفيديو بالذكاء الاصطناعي
- **ما تنفذه:** text-to-video، image-to-video، first+last frame transition، video extension، reference-to-video، وتعديل فيديو موجود وإضافة/إزالة عناصر. يذكر حدوداً مثل 3–15 ثانية للتوليد وامتداد تراكمي حتى 30 ثانية، وتصدير حتى 4K وفق مسار API.
- **ملف المهارة:** [SKILL.md](https://github.com/google-gemini/gemini-skills/blob/main/skills/gemini-omni-flash-api/SKILL.md) — محلياً: `skills/upstream/gemini-video-generation/SKILL.md`.
- **آخر تغيير:** [commit 0a70331](https://github.com/google-gemini/gemini-skills/commit/0a70331410aef9ce49d915f926aa86398c607a9e)، 2026-11-05؛ refactor لإزالة config.py وتبسيط generate_video.py.
- **الترخيص:** Apache-2.0، محفوظ.
- **المتطلبات:** Python 3.10+، google-genai >=2.30.1، ffmpeg/ffprobe لبعض المعالجة، GEMINI_API_KEY. التكلفة الفعلية لم تُثبت من SKILL.md، لذا لا أضع سعراً. يتطلب اتصالاً بالإنترنت.
- **قيود:** رفع فيديوهات المصدر للتحرير/الامتداد/المراجع غير متاح في EEA وسويسرا والمملكة المتحدة وبعض الولايات الأمريكية بحسب تحذير المهارة. يجب التحقق من أهلية الحساب والمنطقة والتسعير قبل الاستخدام.
- **ChatGPT:** يحتاج API خارجي ومفتاح وسكربتات محلية؛ لا يعني وجود الملف أن التوليد متاح داخل ChatGPT.
- **التقييم:** مرتفع جداً لتوليد الفيديو متعدد الوسائط، مع اعتماد قوي على API وحدود نموذج/منطقة.
- **المستودع:** https://github.com/google-gemini/gemini-skills

### 7) YouTube Skill — تجهيز النشر وSEO والصورة المصغرة
- **ما تنفذه:** تفريغ الفيديو، استخراج عبارات بحث من autocomplete، صياغة 10 عناوين ووصف وفصول وtags/hashtags، فحص حدود الحقول، تجهيز خيارات thumbnails من إطارات الفيديو ومراجعتها بحجم feed، ثم رفع عبر WoopSocial بعد الموافقة.
- **ملف المهارة:** [SKILL.md](https://github.com/social-media-skills/youtube-skill/blob/main/skills/youtube-skill/SKILL.md) — محلياً: `skills/upstream/youtube-publishing/SKILL.md`.
- **آخر تغيير:** [commit 14cf912](https://github.com/social-media-skills/youtube-skill/commit/14cf912ba9de1f873f9d34a125176da9439d3867)، 2026-11-02؛ الإصدار 1.0.0.
- **الترخيص:** MIT، محفوظ.
- **المتطلبات:** FFmpeg وPillow؛ faster-whisper محلي أو Groq/OpenAI API؛ YouTube Data API key اختياري لإظهار ترتيب وviews/videos؛ WoopSocial للرفع.
- **ChatGPT:** يمكن إعادة استخدام rubric وكتابة metadata؛ الرفع يتطلب connector وحساباً مخولاً. المهارة تشترط ألا تكون thumbnail أو claims مضللة وألا ينشر شيء قبل yes.
- **التقييم:** مرتفع لفريق YouTube، لكن نتائج autocomplete وranking تتأثر باللغة والمنطقة والوقت ولا تضمن ترتيباً.
- **المستودع:** https://github.com/social-media-skills/youtube-skill

### 8) YouTube Long-form — استراتيجية نمو الفيديو الطويل
- **ما تنفذه:** يفرق بين بوابة CTR (العنوان/الصورة المصغرة) وبوابة retention، ويبني استراتيجية وتغليفاً وسكربتات طويلة، ويوجه للتحليل في YouTube Studio. ليس أداة مونتاج.
- **ملف المهارة:** [SKILL.md](https://github.com/social-media-skills/skills/blob/main/skills/youtube-long-form/SKILL.md) — محلياً: `skills/upstream/youtube-long-form/SKILL.md`.
- **آخر تغيير للملف:** [commit 2e54555](https://github.com/social-media-skills/skills/commit/2e54555c38c59610a4cf1f81f452f7dfe2623233)، 2026-07-16؛ الإصدار 1.0.0.
- **الترخيص:** MIT على مستوى المستودع، تم التحقق من LICENSE؛ ملف المهارة لا يحمل تصريحاً منفصلاً في frontmatter.
- **المتطلبات:** يعتمد على sibling skills مثل brand-profile وvoice-builder وworkflow النشر/التحليلات؛ قد يتطلب WoopSocial وYouTube Studio.
- **ChatGPT:** مناسب كتعليمات استراتيجية بعد تكييف الروابط/المهارات الشقيقة؛ analytics ليست متاحة دون إدخال بيانات أو connector.
- **التقييم:** مرتفع للاستراتيجية، متوسط للتنفيذ المستقل بسبب الاعتماد على مهارات شقيقة.
- **المستودع:** https://github.com/social-media-skills/skills

### 9) Analyze Video Editing — تحليل مرجعي إطارياً واستخراج grammar بصري
- **ما تنفذه:** تحليل micro timeline وmacro grammar، shot boundaries ومددها، الحركة/الكاميرا/التكوين، الحوار والصوت والموسيقى والعناوين والإيقاع، وفصل measured/observed/interpreted لتقليل الادعاءات الوهمية. ينتج evidence table وcontact sheet وframes/strips.
- **ملف المهارة:** [SKILL.md](https://github.com/gitethanwoo/video-editing/blob/main/skills/analyze-video-editing/SKILL.md) — محلياً: `skills/upstream/analyze-video-editing/SKILL.md`.
- **آخر تغيير معروف:** [commit 166eed9](https://github.com/gitethanwoo/video-editing/commit/166eed9b1f391af5201a37057924593bf8f413d4)، 2026-07-29؛ أُضيفت مهارة B-roll المجاورة. لم أجد في سجل path lookup تغييراً أحدث لهذا الملف.
- **الترخيص:** MIT للمستودع، محفوظ.
- **المتطلبات:** سكربتات Python وFFmpeg وأدوات تحليل الفيديو؛ مسار audio_listener الاختياري يستخدم GEMINI_API_KEY. لا تُوزّع الفيديو المرجعي.
- **ChatGPT:** يمكن تحليل لقطات/مقاطع متاحة ضمن حدود الإدخال، لكن استخراج contact sheets والقياسات يتطلب أدوات خارجية.
- **التقييم:** مرتفع جداً للتعلم من الأسلوب دون نسخ العمل؛ ممتاز في التمييز بين الدليل والفرضية.
- **المستودع:** https://github.com/gitethanwoo/video-editing

### 10) Find B-roll — البحث عن لقطات داعمة مع provenance
- **ما تنفذه:** يحول transcript إلى beat plan مرتبط بكلمات محددة، يختار route للمصدر (receipt/entity/product/concept/archival/cultural)، يسجل المصدر والحقوق والوقت، يضع B-roll بعد anchor word، ثم يراجع المخرجات بصرياً.
- **ملف المهارة:** [SKILL.md](https://github.com/gitethanwoo/video-editing/blob/main/skills/find-broll/SKILL.md) — محلياً: `skills/upstream/find-broll/SKILL.md`.
- **آخر تغيير معروف:** [commit 166eed9](https://github.com/gitethanwoo/video-editing/commit/166eed9b1f391af5201a37057924593bf8f413d4)، 2026-07-29.
- **الترخيص:** المستودع MIT؛ المنهج يستند إلى B-Roll Finder بترخيص MIT، لكن كل footage طرف ثالث يحتفظ بحقوقه وشروطه.
- **المتطلبات:** بحث ويب/مصادر موثوقة، transcript أو video/audio، manifest، وورشة rendering الشقيقة. التحميل التجاري/النشر أو تسجيل الدخول يتطلب موافقة منفصلة.
- **ChatGPT:** ممتاز لتخطيط اللقطات والبحث والتوثيق؛ وضعها على timeline يحتاج أدوات تحرير محلية.
- **التقييم:** مرتفع جداً للـ provenance والامتثال؛ يرفض تخمين التراخيص أو اختيار memes عشوائياً.
- **المستودع:** https://github.com/gitethanwoo/video-editing

### 11) After Effects — Expressions وMOGRT وExport وProject hygiene
- **ما تنفذه:** expressions (wiggle/loopOut/bounce)، rigging عبر null/slider، MOGRT، التصدير مع alpha/ProRes/H.264/AME، performance triage، relinking، تنظيم المشروع وExtendScript scripts.
- **ملف المهارة:** [SKILL.md](https://github.com/iart-ai/motion-design-skills/blob/main/skills/after-effects/SKILL.md) — محلياً: `skills/upstream/after-effects/SKILL.md`.
- **آخر تغيير للملف المتحقق:** [commit 3110f14](https://github.com/iart-ai/motion-design-skills/commit/3110f145d92bfbb0d3da88940de6c50225b79bf7)، 2026-06-22 (إعادة تنظيم المسارات وإضافة manifest للـ plugin).
- **الترخيص:** MIT للمستودع، محفوظ.
- **المتطلبات:** Adobe After Effects، وغالباً Adobe Media Encoder للتسليم؛ ExtendScript/JavaScript داخل AE. اشتراك Adobe والتكاليف غير محددة في الملف.
- **ChatGPT:** مناسب لتوليد تعبيرات وJSX وتعليمات إصلاح، لكن لا يتحكم بواجهة AE أو يصدّر ملفاً دون desktop automation.
- **التقييم:** مرتفع؛ منظم حسب symptom مع أمثلة فعلية، لكن معلومات الإصدارات قد تحتاج مراجعة عند تحديث AE.
- **المستودع:** https://github.com/iart-ai/motion-design-skills

### 12) Blender Animation — keyframes وNLA وMocap وRetargeting
- **ما تنفذه:** نظام Actions/slots/layers/channelbags في Blender 5.x، keyframe blocking/breakdowns/spline/polish، loop seam checks، root motion، bake control rigs، BVH/Mixamo retargeting، NLA وpose libraries وتصدير FBX/glTF.
- **ملف المهارة:** [SKILL.md](https://github.com/EL4CTEO/blender-skills/blob/main/skills/blender-animation/SKILL.md) — محلياً: `skills/upstream/blender-animation/SKILL.md`.
- **آخر تغيير:** [commit 53c308e](https://github.com/EL4CTEO/blender-skills/commit/53c308e9f686436960473f5f535fae2b7e738ddc)، 2026-11-13؛ release 1.3.0 أضاف دعم Blender 5.3، والملف نفسه يحمل metadata version 1.2.0.
- **الترخيص:** MIT، محفوظ.
- **المتطلبات:** Blender 5.3 للمسارات الحديثة وPython API `bpy`; scripts داخل المستودع. Mixamo/BVH inputs؛ Rokoko مجاني حسب المهارة، Auto-Rig Pro مدفوع، وممكن UE/Unity retarget pipelines.
- **ChatGPT:** يمكن توليد أو مراجعة Python snippets؛ التشغيل يحتاج Blender GUI أو background process على جهاز المستخدم.
- **التقييم:** مرتفع جداً للأنيميشن التقني وgame pipelines؛ حساس لتغيرات API بين إصدارات Blender.
- **المستودع:** https://github.com/EL4CTEO/blender-skills

### 13) Blender Previs & Storyboard — تحويل النص إلى shot list/animatic
- **ما تنفذه:** تفكيك script إلى beats وshot list، اختيار الكاميرا والعدسة وارتفاع الكاميرا وقاعدة 180° واتجاه الشاشة وحجم اللقطة والحركة والمدة، وتجميع stills في Video Sequencer/animatic.
- **ملف المهارة:** [SKILL.md](https://github.com/scenario-labs/skills/blob/main/skills/dcc/blender/scenario-blender-previs-storyboard/SKILL.md) — محلياً: `skills/upstream/blender-previs-storyboard/SKILL.md`.
- **آخر تغيير:** [commit b8544b9](https://github.com/scenario-labs/skills/commit/b8544b9c86e0685844cc6effbb27f3885f744d3a)، 2026-10-29؛ شدّد تثبيت الإصدارات والتحقق من hash للخطوات والأصول في مجموعة المهارات.
- **الترخيص:** MIT، محفوظ.
- **المتطلبات:** Blender 5.2.1 موضح كإصدار اختبار للـ toolkit؛ يتطلب sibling skill باسم scenario-blender-expert وقناة تنفيذ Scenario MCP أو تكييف scripts يدوياً.
- **ChatGPT:** لا يعمل وحده؛ يحتاج Scenario MCP أو Blender محلياً وتحميل المهارات الشقيقة.
- **التقييم:** مرتفع للتخطيط البصري والـ previs؛ الاعتماد على منظومة Scenario يجعل نقله إلى ChatGPT العادي يحتاج تهيئة كبيرة.
- **المستودع:** https://github.com/scenario-labs/skills

### 14) Caption Styling — توقيت وترتيب captions آمن للمنصات
- **ما تنفذه:** يضع معايير طول السطر وسرعة القراءة ومدة cue وحجم الخط والتباين ومناطق الأمان في TikTok/Reels/Shorts، ويتحقق من SRT/VTT؛ يقدم recipes للحرق عبر FFmpeg/libass.
- **ملف المهارة:** [SKILL.md](https://github.com/vidmoat/skills/blob/main/skills/core/caption-styling/SKILL.md) — محلياً: `skills/upstream/caption-styling/SKILL.md`.
- **آخر تغيير:** [commit 0554420](https://github.com/vidmoat/skills/commit/05544203cd4e8978654d65320c983c39b23bd3ba)، 2026-10-02؛ صحح تقاطع safe-zone بين TikTok وReels، وفحص الملاءمة وحد 32 حرفاً الافتراضي.
- **الترخيص:** نص SKILL.md هو CC-BY-4.0؛ سكربتات المستودع Apache-2.0. رابط الترخيص: https://creativecommons.org/licenses/by/4.0/ . ملف LICENSE العام للمستودع Apache يخص الكود وليس نص المهارة.
- **المتطلبات:** توجيه عام لأي محرر؛ checker يحتاج Python 3.8+ standard library؛ burn-in يحتاج FFmpeg مبنيّاً مع libass.
- **ChatGPT:** جيد كمرجع ومراجعة subtitles؛ التحقق الآلي يتطلب Python.
- **التقييم:** مرتفع ومحدد، والتحديث الأخير يعالج خطأً عملياً في safe zones.
- **المستودع:** https://github.com/vidmoat/skills

### 15) Audio Ducking — موازنة الموسيقى تحت التعليق الصوتي
- **ما تنفذه:** تحديد مستوى music bed، ducking عند الكلام دون pumping، envelope أو sidechain، mastering إلى loudness target مناسب لـYouTube/podcast/broadcast.
- **ملف المهارة:** [SKILL.md](https://github.com/vidmoat/skills/blob/main/skills/core/audio-ducking/SKILL.md) — محلياً: `skills/upstream/audio-ducking/SKILL.md`.
- **آخر تغيير معروف:** [commit b417800](https://github.com/vidmoat/skills/commit/b4178000dd63feea8b481653ad145418b07eb2c2)، 2026-10-01 (إنشاء حزمة المهارات العامة). لا يظهر في سجل المسار commit أحدث ضمن ما تحققنا منه.
- **الترخيص:** نص المهارة CC-BY-4.0؛ scripts Apache-2.0؛ تفاصيل الترخيص في https://creativecommons.org/licenses/by/4.0/ .
- **المتطلبات:** tool-agnostic؛ envelope script يحتاج Python 3.8+ standard library؛ وصفات FFmpeg تحتاج 4.4+؛ لا مفتاح API.
- **ChatGPT:** يمكن تطبيق القواعد على mix plan؛ التشغيل الفعلي يتطلب محرر صوت أو FFmpeg.
- **التقييم:** مرتفع لتسليم صوت ثابت، مع defaults واضحة ومستقلة عن برنامج بعينه.
- **المستودع:** https://github.com/vidmoat/skills

### 16) Adobe Batch Edit Photos — توحيد معالجة مجموعة صور
- **ما تنفذه:** يطبق تعديلات موحدة على عدة صور: auto straighten/tone، adjustments/presets، اختيار subject، effects/blur، crop/resize، معاينة مجمعة، وخيار Firefly Board.
- **ملف المهارة:** [SKILL.md](https://github.com/adobe/skills/blob/main/plugins/creative-cloud/adobe-for-creativity/skills/adobe-batch-edit-photos/SKILL.md) — محلياً: `skills/upstream/adobe-batch-photo-edit/SKILL.md`.
- **آخر تغيير:** [commit 59140a5](https://github.com/adobe/skills/commit/59140a57066a760d9c00c1380082d5b7c901556a)، 2026-10-23؛ حذف أوامر curl من تعليمات المهارة.
- **الترخيص:** Apache-2.0 في frontmatter والمستودع؛ محفوظ.
- **المتطلبات:** تسجيل دخول Adobe مطلوب؛ يعتمد على قائمة أدوات Adobe محددة (مثل image_apply_adjustments وasset_add_file وasset_preview_file). مهارة التكامل ليست workflow محلياً مستقلاً. السعر/الخطة المطلوبة غير موضحين.
- **ChatGPT:** يحتاج Adobe connector والأدوات المعتمدة، ولا يمكن اعتبارها قابلة للتنفيذ في ChatGPT العادي بمجرد نسخ SKILL.md.
- **التقييم:** مرتفع إذا كان تكامل Adobe متاحاً، وإلا فالفائدة المباشرة محدودة.
- **المستودع:** https://github.com/adobe/skills

## أدوات ومكتبات واعدة — ليست Agent Skills مستقلة

- **FFmpeg/ffprobe:** محرك التحويل والقص والـ probing لعدد كبير من المهارات؛ https://ffmpeg.org/ . يتطلب تثبيتاً محلياً.
- **faster-whisper:** تفريغ محلي بكلمات وتوقيتات، مستخدم في تحرير المتحدث وShorts وYouTube؛ https://github.com/SYSTRAN/faster-whisper . يحتاج Python وموارد CPU/GPU مناسبة.
- **Google Gemini Interactions API / google-genai:** توليد وتعديل الفيديو في مهارة Gemini؛ https://github.com/googleapis/python-genai . يتطلب مفتاحاً وحساباً واستخداماً سحابياً.
- **Remotion + React/SVG:** مشاهد وعناوين ومخططات موشن قابلة للبرمجة؛ https://www.remotion.dev/ . يتطلب Node ومشروع React.
- **Blender Python API (bpy):** أنيميشن وrigging وprevis وrendering؛ https://docs.blender.org/api/current/ . يتطلب Blender متوافقاً.
- **WoopSocial:** ربط النشر للمنصات من عدة مهارات اجتماعية؛ ليس مكوناً مدمجاً في ChatGPT ويحتاج حساباً وتفويضاً. السعر وحدود الخطة غير مثبتين هنا.
- لم أضم مخازن stock أو خطوطاً أو LUTs أو SFX كأنها مهارات؛ لم أتحقق في هذه الجولة من ترخيص أصول محددة تصلح لإعادة التوزيع التجاري.

## التوافق مع ChatGPT: الحكم العام

وجود `SKILL.md` على GitHub لا يثبت تثبيته داخل ChatGPT ولا يعني أن أدواته التنفيذية متاحة. ملفات التعليمات النصية يمكن تكييفها إلى workflow أو تعليمات، لكن:
- CLI/FFmpeg/Blender/After Effects/Remotion تحتاج جهازاً أو بيئة تنفيذ خارج ChatGPT.
- Gemini/Whisper/Groq/OpenAI وAdobe تحتاج مفاتيح/حسابات/موصلات عند تشغيلها.
- WoopSocial/Scenario MCP يتطلبان التكامل وتفويض الحساب.
- لا تضع مفاتيح API في ملفات المستودع؛ استخدم متغيرات بيئة أو خزائن أسرار محلية.
- لم أختبر تشغيل أي سكربت أو API أو نشر فعلي ضمن هذه الجولة.

## حدود التغطية

هذه جولة بحث واسعة لكنها ليست ضماناً باكتشاف كل SKILL.md عام على GitHub. لم أتحقق من كل fork أو كل أداة في جميع المجالات، ولم أضم أي نتيجة لم أفتح ملف SKILL.md الفعلي لها. لم أجد في المواد التي تحققت منها دليلاً كافياً لإضافة مهارة مستقلة متخصصة في Final Cut Pro أو CapCut أو Audition أو Cinema 4D أو Unreal Engine أو DaVinci Resolve؛ هذا لا يعني عدم وجودها. لا تعتبر تاريخ commit للمستودع دليلاً على تغيير جوهري في ملف المهارة ما لم يمس الملف نفسه.
