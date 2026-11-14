# تقرير البحث والتحقق — Agent Skills لصناعة المحتوى والفيديو والصوت والتصميم
**تاريخ الفحص: 14 نوفمبر 2026**

## الملخص التنفيذي
تم التحقق من وجود وقراءة 26 ملف SKILL.md فعلياً من GitHub ونسخها إلى هذا المستودع. المجموعة الأقوى تنفيذياً: FFmpeg Skill وTyped Video Editing وMedia Studio وVideo to Shorts وTalking-head Editing. للتوليد بالذكاء الاصطناعي: Gemini Omni Flash. للأنيميشن والتخطيط: Blender Animation وBlender Previs. للصوت: Audio Mixing & Mastering وAudio Ducking. للنشر: YouTube Publishing وYouTube Long-form.

## بطاقات موجزة مع الأدلة والمتطلبات

### 1) FFmpeg Skill
- **المجال والتنفيذ:** قص ودمج وإعادة تأطير وتغيير سرعة وعناوين وoverlays وkeying وcaptions وصمت ومزامنة وصوت وLUFS وHDR-to-SDR وproxy وmulticam وتصدير وفحص. يوجه كل طلب إلى script محدد ويفرض probe ثم dry-run ثم تنفيذ وcheck/verify.
- **المصادر:** [SKILL.md](https://github.com/kajisho5/ffmpeg-skill/blob/main/SKILL.md) · [المستودع](https://github.com/kajisho5/ffmpeg-skill) · [commit الملف](https://github.com/kajisho5/ffmpeg-skill/commit/18aa2402c887c927e59169fc2946b9dc5b3e1545) — 14 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ FFmpeg 6.1+ وPython 3.10+؛ تنفيذ CLI محلي ويحتاج scripts/references من المستودع.
- **ChatGPT/التقييم:** ممتاز كتعليمات توجيه وفحص؛ التنفيذ يتطلب CLI وملفات محلية. لا يتخذ قرارات الذوق أو أفضل cut، وSKILL.md وحده لا يكفي لأن scripts وreferences لم تنسخ.

### 2) Typed Video Editing
- **المجال والتنفيذ:** تنفيذ trim/cut/concat/speed/fit/fill/resize/overlay عبر طلب typed مع خريطة source-to-timeline وprovenance وSHA-256 وprobe. يرفض shell commands وfilter strings الحرة.
- **المصادر:** [SKILL.md](https://github.com/kajisho5/video-editing-skill/blob/main/SKILL.md) · [المستودع](https://github.com/kajisho5/video-editing-skill) · [commit 0.8.0 / contract 7.0](https://github.com/kajisho5/video-editing-skill/commit/5134734adbb9f2dc6123548d523aea6bf6cb9189) — 13 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ Python 3.9+ وFFmpeg/ffprobe وffmpeg-skill CLI.
- **ChatGPT/التقييم:** ممتاز للقص المتكرر القابل للتدقيق؛ التخطيط ممكن داخل ChatGPT، التنفيذ يتطلب CLI. لا يقرر ما الذي يجب قصه، بل ينفذ قراراً محدداً.

### 3) Video Editing Workbench
- **المجال والتنفيذ:** workflow شامل يفحص المصادر ويخطط timeline ويولد contact sheets وtransition strips وstills ثم يرندر ويفحص النتيجة؛ يضم مهارات تحليل الفيديو وB-roll.
- **المصادر:** [SKILL.md](https://github.com/gitethanwoo/video-editing/blob/main/skills/video-editing/SKILL.md) · [المستودع](https://github.com/gitethanwoo/video-editing) · [commit](https://github.com/gitethanwoo/video-editing/commit/166eed9b1f391af5201a37057924593bf8f413d4) — 29 Jul 2026.
- **الترخيص والمتطلبات:** MIT؛ Python وFFmpeg، وNode/React لمسار Remotion.
- **ChatGPT/التقييم:** مرتفع جداً لسير العمل؛ scripts وreferences الخارجية غير مرفقة هنا.

### 4) Video to Shorts
- **المجال والتنفيذ:** transcript مع توقيت الكلمات، اقتراح لحظات، تقييم hook/payoff/standalone، vertical render وcaptions ثم تكامل نشر بعد موافقة.
- **المصادر:** [SKILL.md](https://github.com/social-media-skills/video-to-shorts-skill/blob/main/skills/video-to-shorts-skill/SKILL.md) · [المستودع](https://github.com/social-media-skills/video-to-shorts-skill) · [commit](https://github.com/social-media-skills/video-to-shorts-skill/commit/b5f3c4087791be00fc9740d3b507c82719e3d295) — 29 Oct 2026.
- **الترخيص والمتطلبات:** MIT؛ FFmpeg/Pillow، faster-whisper محلي أو Groq/OpenAI API، وWoopSocial للنشر. تكلفة API تتغير وغير محسومة في الملف.
- **ChatGPT/التقييم:** ممتاز لإعادة التوظيف؛ تشغيل transcription/render/post يتطلب API أو runtime خارجي وموافقة على الحسابات.

### 5) Talking-head Editing
- **المجال والتنفيذ:** تحرير talking-head/podcast/course؛ transcript، حذف الصمت والحشو والتأتأة والretakes، punch-ins وتنظيف الصوت وcaptions وchapters وvertical exports؛ موافقة على خطة القص.
- **المصادر:** [SKILL.md](https://github.com/social-media-skills/video-editing-skill/blob/main/skills/video-editing-skill/SKILL.md) · [المستودع](https://github.com/social-media-skills/video-editing-skill) · [commit](https://github.com/social-media-skills/video-editing-skill/commit/4ba4092ab946a991d84087e2aa1408dc2c3e1cb2) — 11 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ FFmpeg/Pillow، faster-whisper أو Groq/OpenAI API، وWoopSocial للنشر.
- **ChatGPT/التقييم:** قوي في محتوى الكلام؛ يستلزم مراجعة بشرية للمعنى قبل اعتماد القص، مع CLI/API للرندر.

### 6) Gemini Omni Flash API
- **المجال والتنفيذ:** text-to-video وimage/video reference وfirst/last-frame وvideo extension وتحرير فيديو موجود وbatch jobs.
- **المصادر:** [SKILL.md](https://github.com/google-gemini/gemini-skills/blob/main/skills/gemini-omni-flash-api/SKILL.md) · [المستودع](https://github.com/google-gemini/gemini-skills) · [commit](https://github.com/google-gemini/gemini-skills/commit/0a70331410aef9ce49d915f926aa86398c607a9e) — 5 Nov 2026.
- **الترخيص والمتطلبات:** Apache-2.0؛ Python 3.10+ وgoogle-genai وGEMINI_API_KEY وFFmpeg للتحضير؛ API خارجي مدفوع/وفق شروط Google الحالية، والسعر غير ثابت هنا.
- **ChatGPT/التقييم:** مهم جداً للتوليد، لكن التنفيذ يتطلب حساباً ومفتاحاً وملفات؛ توجد قيود إقليمية موثقة على بعض عمليات رفع/تحرير الفيديو.

### 7) YouTube Publishing
- **المجال والتنفيذ:** autocomplete، كلمات بحث، عناوين ووصف وفصول وtags وthumbnail وتجهيز/تنفيذ الرفع بعد موافقة.
- **المصادر:** [SKILL.md](https://github.com/social-media-skills/youtube-skill/blob/main/skills/youtube-skill/SKILL.md) · [المستودع](https://github.com/social-media-skills/youtube-skill) · [commit v1](https://github.com/social-media-skills/youtube-skill/commit/14cf912ba9de1f873f9d34a125176da9439d3867) — 2 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ FFmpeg/Pillow، transcription محلي أو API، YouTube Data API اختياري، WoopSocial للرفع.
- **ChatGPT/التقييم:** جيد لتجهيز metadata؛ الرفع يحتاج OAuth/connectors ولا يضمن SEO ترتيباً أو مشاهدات.

### 8) YouTube Long-form
- **المجال والتنفيذ:** استراتيجية الفيديو الطويل والتغليف والموضوع والسكريبت وتحسين CTR والاحتفاظ.
- **المصادر:** [SKILL.md](https://github.com/social-media-skills/skills/blob/main/skills/youtube-long-form/SKILL.md) · [المستودع](https://github.com/social-media-skills/skills) · [commit](https://github.com/social-media-skills/skills/commit/2e54555c38c59610a4cf1f81f452f7dfe2623233) — 16 Jul 2026.
- **الترخيص والمتطلبات:** MIT للمستودع؛ بيانات YouTube Studio ومهارات شقيقة مثل brand-profile/voice مفيدة؛ لم يثبت الملف API إلزامياً.
- **ChatGPT/التقييم:** مناسب للاستراتيجية والسكريبت؛ التحليلات تحتاج بيانات القناة الفعلية، ولا يضمن النمو.

### 9) Analyze Video Editing
- **المجال والتنفيذ:** تحليل shot/cut/fade/camera motion/dialogue/subtitles/music/sound/pacing مع تمييز القياس عن التفسير.
- **المصادر:** [SKILL.md](https://github.com/gitethanwoo/video-editing/blob/main/skills/analyze-video-editing/SKILL.md) · [المستودع](https://github.com/gitethanwoo/video-editing) · [commit](https://github.com/gitethanwoo/video-editing/commit/166eed9b1f391af5201a37057924593bf8f413d4) — 29 Jul 2026.
- **الترخيص والمتطلبات:** MIT؛ Python/FFmpeg، وربما Gemini API لمسار استماع اختياري.
- **ChatGPT/التقييم:** قوي للتعلم من المقاطع؛ extraction يتطلب أدوات، ويجب ألا يتحول التحليل إلى نسخ محمي.

### 10) Find B-roll
- **المجال والتنفيذ:** transcript إلى beat plan، البحث عن لقطات داعمة، وتسجيل provenance والترخيص والتوقيت.
- **المصادر:** [SKILL.md](https://github.com/gitethanwoo/video-editing/blob/main/skills/find-broll/SKILL.md) · [المستودع](https://github.com/gitethanwoo/video-editing) · [commit](https://github.com/gitethanwoo/video-editing/commit/166eed9b1f391af5201a37057924593bf8f413d4) — 29 Jul 2026.
- **الترخيص والمتطلبات:** MIT للمهارة؛ ترخيص كل footage منفصل. يحتاج بحث مصادر ومحرر فيديو.
- **ChatGPT/التقييم:** ممتاز لإثبات المصدر؛ لا يجعل اللقطات مجانية أو مسموحاً بإعادة استخدامها.

### 11) After Effects
- **المجال والتنفيذ:** expressions وrigging وMOGRT وLottie وExtendScript والتصدير وتحسين الأداء.
- **المصادر:** [SKILL.md](https://github.com/iart-ai/motion-design-skills/blob/main/skills/after-effects/SKILL.md) · [المستودع](https://github.com/iart-ai/motion-design-skills) · [commit](https://github.com/iart-ai/motion-design-skills/commit/3110f145d92bfbb0d3da88940de6c50225b79bf7) — 22 Jun 2026.
- **الترخيص والمتطلبات:** MIT؛ Adobe After Effects؛ بعض export workflows تحتاج Media Encoder/Lottie، واشتراك Adobe حسب الخطة.
- **ChatGPT/التقييم:** جيد لتوليد expressions والشرح؛ لا يفتح AE أو ينفذ render من دون برنامج/connector.

### 12) Blender Animation
- **المجال والتنفيذ:** keyframes وActions وF-curves وNLA وmocap/BVH/Mixamo retarget وbaking/root motion والتصدير.
- **المصادر:** [SKILL.md](https://github.com/EL4CTEO/blender-skills/blob/main/skills/blender-animation/SKILL.md) · [المستودع](https://github.com/EL4CTEO/blender-skills) · [release 1.3.0 / Blender 5.3](https://github.com/EL4CTEO/blender-skills/commit/53c308e9f686436960473f5f535fae2b7e738ddc) — 13 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ Blender 5.3 وbpy؛ Auto-Rig Pro اختياري ومدفوع إن استُخدم.
- **ChatGPT/التقييم:** ممتاز تقنياً؛ يلزم Blender فعلي لتشغيل Python API والرندر، والانتباه لتغير API.

### 13) Blender Previs & Storyboard
- **المجال والتنفيذ:** script إلى beats وshot list وتكوين وكاميرا وعدسة وscreen direction وقاعدة 180° ومدد وanimatic.
- **المصادر:** [SKILL.md](https://github.com/scenario-labs/skills/blob/main/skills/dcc/blender/scenario-blender-previs-storyboard/SKILL.md) · [المستودع](https://github.com/scenario-labs/skills) · [commit](https://github.com/scenario-labs/skills/commit/b8544b9c86e0685844cc6effbb27f3885f744d3a) — 29 Oct 2026.
- **الترخيص والمتطلبات:** MIT؛ Blender (المختبر وفق الملف على 5.2.1) وScenario MCP وsibling skill/toolkit.
- **ChatGPT/التقييم:** مناسب للتخطيط؛ animatic يحتاج Blender وتكامل MCP، وليس مستقلاً.

### 14) Caption Styling
- **المجال والتنفيذ:** طول السطر وسرعة القراءة وتوقيت cue والتباين والحجم وsafe zones والتحقق من SRT/VTT.
- **المصادر:** [SKILL.md](https://github.com/vidmoat/skills/blob/main/skills/core/caption-styling/SKILL.md) · [المستودع](https://github.com/vidmoat/skills) · [safe-zone commit](https://github.com/vidmoat/skills/commit/05544203cd4e8978654d65320c983c39b23bd3ba) — 2 Oct 2026.
- **الترخيص والمتطلبات:** Apache-2.0 على مستوى المستودع؛ قد تختلف تراخيص scripts الفرعية. Python وFFmpeg/libass للحرق.
- **ChatGPT/التقييم:** جيد لفحص النص وتقسيمه؛ الرندر خارجي، وليس transcription أو ترجمة تلقائية.

### 15) Audio Ducking
- **المجال والتنفيذ:** مستويات music bed وducking تحت الحوار من timestamps أو sidechain مع تقليل pumping وتحديد loudness.
- **المصادر:** [SKILL.md](https://github.com/vidmoat/skills/blob/main/skills/core/audio-ducking/SKILL.md) · [المستودع](https://github.com/vidmoat/skills) · [commit](https://github.com/vidmoat/skills/commit/b4178000dd63feea8b481653ad145418b07eb2c2) — 1 Oct 2026.
- **الترخيص والمتطلبات:** CC-BY-4.0 لنص المهارة وفق frontmatter؛ Apache-2.0 للسكربتات. Python أو FFmpeg/DAW حسب التنفيذ.
- **ChatGPT/التقييم:** مفيد للتخطيط؛ يجب الاستماع النهائي، ولا يكفي رقم LUFS وحده.

### 16) Adobe Batch Photo Edit
- **المجال والتنفيذ:** توحيد دفعة صور باستخدام auto tone/straighten/presets/subject selection/effects/crop/resize/preview.
- **المصادر:** [SKILL.md](https://github.com/adobe/skills/blob/main/plugins/creative-cloud/adobe-for-creativity/skills/adobe-batch-edit-photos/SKILL.md) · [المستودع](https://github.com/adobe/skills) · [commit](https://github.com/adobe/skills/commit/59140a57066a760d9c00c1380082d5b7c901556a) — 23 Oct 2026.
- **الترخيص والمتطلبات:** Apache-2.0 للمستودع؛ Adobe sign-in وأدوات Creative Cloud/connector. الاشتراك حسب خطة Adobe.
- **ChatGPT/التقييم:** عالي مع تكامل Adobe صالح؛ الملف وحده لا يعني وجود اتصال Adobe في هذه الجلسة.

### 17) Photoshop Expert
- **المجال والتنفيذ:** retouching وcompositing وselection/masking وdigital painting وlayer-based design وbatch actions وprint prep.
- **المصادر:** [SKILL.md](https://github.com/theneoai/awesome-skills/blob/main/skills/tool/design/photoshop-expert/SKILL.md) · [المستودع](https://github.com/theneoai/awesome-skills) · [commit](https://github.com/theneoai/awesome-skills/commit/493698741eee39532b1dd9968a5aa4d63f935c77) — 30 Apr 2026.
- **الترخيص والمتطلبات:** MIT مع attribution إضافي إلزامي؛ Photoshop للتطبيق، ولا API/script إلزامي في الملف.
- **ChatGPT/التقييم:** متوسط؛ نص إرشادي واسع لكنه يحتوي أمثلة عامة/حشو وبعض توصيات resolution مبسطة، فلا أعدّه أداة أتمتة Photoshop عميقة.

### 18) Audio Mixing & Mastering
- **المجال والتنفيذ:** audio contract، foreground hierarchy، deliverables/stems، monitoring assumptions، loudness/true peak/intelligibility/accessibility وQC.
- **المصادر:** [SKILL.md](https://github.com/calesthio/generative-media-skills/blob/main/skills/production/audio-craft/audio-mixing-mastering/SKILL.md) · [المستودع](https://github.com/calesthio/generative-media-skills) · [commit](https://github.com/calesthio/generative-media-skills/commit/079f952442db3f86d5016c83175020c5ed07bedb) — 12 Jul 2026.
- **الترخيص والمتطلبات:** MIT؛ مهارة provider-independent، لكن المعالجة تحتاج DAW/مقاييس/أدوات حسب المهمة؛ لا API أو GPU إلزامي في النص.
- **ChatGPT/التقييم:** عميقة للتخطيط وQC؛ mastering الفعلي والاستماع يحتاجان أدوات خارجية، ويجب اتباع مواصفات العميل لا target عام.

### 19) Media Studio
- **المجال والتنفيذ:** probe-plan-process-verify للفيديو والصوت والصور والأنيميشن، استعادة الحاويات، denoise/deband/upscale وloudness mastering وquality gates.
- **المصادر:** [SKILL.md](https://github.com/hadbilen/antigravity-harness/blob/main/skills/media-studio/SKILL.md) · [المستودع](https://github.com/hadbilen/antigravity-harness) · [commit](https://github.com/hadbilen/antigravity-harness/commit/153623d1e4d776c40b7a708def171fdc19bd9567) — 29 Oct 2026.
- **الترخيص والمتطلبات:** MIT؛ scripts محلية وFFmpeg/Python واعتمادات معالجة حسب الوظيفة؛ لا أجزم بمتطلب GPU/API عام.
- **ChatGPT/التقييم:** واعدة وعميقة؛ لكنها تعتمد على ملفات وأدوات runtime لم تُنسخ هنا. لا يكفي SKILL.md وحده.

### 20) FilmCraft Expert
- **المجال والتنفيذ:** قص ومونتاج وmulticam/proxy/captions/titles/transitions/keyframes/time remapping/LUTs/chroma key/mix/export/archive عبر NLE MCP.
- **المصادر:** [SKILL.md](https://github.com/fralapo/awesome-agent-skills/blob/main/skills/filmcraft-expert/SKILL.md) · [المستودع](https://github.com/fralapo/awesome-agent-skills) · [commit](https://github.com/fralapo/awesome-agent-skills/commit/b169016ec6aae764931f919e9ae38a3819266751) — 12 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ FilmCraft/ArtCraft وخادم MCP بأدوات mcp__filmcraft__*؛ تكاملات إضافية بحسب الصوت/المؤثرات.
- **ChatGPT/التقييم:** تحتاج تركيب MCP وتطبيق NLE خارجي؛ قوية في النطاق لكنها ليست قابلة للتنفيذ تلقائياً هنا.

### 21) CLI-Anything Video Creation
- **المجال والتنفيذ:** مصفوفة قدرات لاختيار أدوات storyboard وstory/audio direction والبحث/التنزيل والتوليد والتحليل والصوت وcaptions وNLE والرندر وQC.
- **المصادر:** [SKILL.md](https://github.com/HKUDS/CLI-Anything/blob/main/cli-hub-matrix/video-creation/SKILL.md) · [المستودع](https://github.com/HKUDS/CLI-Anything) · [commit](https://github.com/HKUDS/CLI-Anything/commit/5b9ec80def29cf0f513ec69894e6c9443c1ca9fa) — 14 Jun 2026.
- **الترخيص والمتطلبات:** Apache-2.0؛ تختلف حسب CLI أو Python library أو binary أو cloud API المختار؛ قد تتطلب API keys أو حسابات مدفوعة.
- **ChatGPT/التقييم:** دليل routing ممتاز، لكنه ليس أداة واحدة ولا يعني أن كل providers مثبتون.

### 22) Vibe Editing Cut
- **المجال والتنفيذ:** inventory للمصادر، transcript word timestamps، EDL بأوقات المصدر والمخرج، إزالة pauses/false starts/fillers، قص frame-accurate وتحريك captions.
- **المصادر:** [SKILL.md](https://github.com/alexey1312/Vibe-Editing-Agent-Skill/blob/main/skills/vibe-editing-cut/SKILL.md) · [المستودع](https://github.com/alexey1312/Vibe-Editing-Agent-Skill) · [commit](https://github.com/alexey1312/Vibe-Editing-Agent-Skill/commit/ef3de0f371246647c8f74ca3d8241d604c664036) — 15 Oct 2026.
- **الترخيص والمتطلبات:** MIT؛ FFmpeg/ffprobe وPython/agent runtime ومحرك تفريغ حسب التهيئة.
- **ChatGPT/التقييم:** مناسب لمراجعة transcript وEDL؛ execution يتطلب shell وملفات. يركز على dialogue edits لا السرد متعدد المشاهد.

### 23) Vibe Editing Review
- **المجال والتنفيذ:** QC للنسخة النهائية: metadata، black/frozen frames، الصوت والصمت/loudness، captions والأسماء والبيانات الحساسة وتقرير أدلة زمنية.
- **المصادر:** [SKILL.md](https://github.com/alexey1312/Vibe-Editing-Agent-Skill/blob/main/skills/vibe-editing-review/SKILL.md) · [المستودع](https://github.com/alexey1312/Vibe-Editing-Agent-Skill) · [commit](https://github.com/alexey1312/Vibe-Editing-Agent-Skill/commit/ef3de0f371246647c8f74ca3d8241d604c664036) — 15 Oct 2026.
- **الترخيص والمتطلبات:** MIT؛ FFmpeg/ffprobe وأدوات محلية؛ توصي بمراجعة بشرية كاملة للصوت والصورة.
- **ChatGPT/التقييم:** مكمل قوي للقص؛ لا يستبدل المشاهدة والاستماع والتحكيم الإبداعي.

### 24) Podcast & Audiograms
- **المجال والتنفيذ:** اختيار podcast clips من transcript وتوقيت الكلمات وبيانات retention، استخدام brand profile وCTA، وإنشاء audiograms اجتماعية.
- **المصادر:** [SKILL.md](https://github.com/social-media-skills/skills/blob/main/skills/podcast-and-audiograms/SKILL.md) · [المستودع](https://github.com/social-media-skills/skills) · [commit](https://github.com/social-media-skills/skills/commit/5222f277a982ef77f5eac86d114c26f6f6223262) — 18 Jul 2026.
- **الترخيص والمتطلبات:** MIT؛ podcast/transcript وbrand profile وبيانات retention إن توفرت؛ أدوات render خارجية حسب التهيئة.
- **ChatGPT/التقييم:** جيدة لإعادة توظيف الحلقات؛ output النهائي يحتاج رندر وتحقق.

### 25) Video EditAgent
- **المجال والتنفيذ:** مهارة تحرير بالفهم الحواري: transcribe/cut/color/overlay/subtitles وتكرار المراجعات على talking-head/montage/tutorial/interview.
- **المصادر:** [SKILL.md](https://github.com/zeonagames/video-editagent/blob/main/SKILL.md) · [المستودع](https://github.com/zeonagames/video-editagent) · [commit](https://github.com/zeonagames/video-editagent/commit/631064f9bb4493c24ba4e9795544241e23d17b11) — 23 Apr 2026.
- **الترخيص والمتطلبات:** لم أعثر على LICENSE في جذر المستودع؛ Unknown/No license. لا توزع أو تستخدم تجارياً قبل التحقق. الأدوات التفصيلية تحتاج مراجعة ملفات المصدر.
- **ChatGPT/التقييم:** تعليمات مبدئية؛ حداثة أقل وترخيص غير مثبت، لذلك درجة الثقة أقل.

### 26) VexJoy Video Editing
- **المجال والتنفيذ:** workflow مونتاج عبر FFmpeg وRemotion وإخراج فيديو من clips أو images أو audio visualizations.
- **المصادر:** [SKILL.md](https://github.com/notque/vexjoy-agent/blob/main/skills/content/video-editing/SKILL.md) · [المستودع](https://github.com/notque/vexjoy-agent) · [commit](https://github.com/notque/vexjoy-agent/commit/fec0a55827aa4df32139f0ea12c5aa68b1e6d955) — 7 Nov 2026.
- **الترخيص والمتطلبات:** MIT؛ Bash/Read/Write وأدوات FFmpeg وNode/Remotion حسب workflow.
- **ChatGPT/التقييم:** جيد كمهارة موجهة لمشروع Agent؛ لا يعمل دون runtime والسكربتات الأصلية.

## أدوات واعدة وليست Agent Skills مستقلة
- [FFmpeg](https://ffmpeg.org/) وffprobe: محرك CLI لتحرير وفحص الوسائط.
- [faster-whisper](https://github.com/SYSTRAN/faster-whisper): تفريغ صوتي محلي.
- [Remotion](https://www.remotion.dev/): فيديو برمجي بـReact.
- [Blender Python API](https://docs.blender.org/api/current/): animation/render scripting.
- [Google Gen AI SDK](https://github.com/googleapis/python-genai): اتصال Gemini API.
- WoopSocial وScenario MCP وFilmCraft MCP: تكاملات خارجية تتطلب حساباً/خادماً وإذن المستخدم.

## حدود هذه الحزمة
1. ما نُسخ هو 26 ملف SKILL.md. لم تُنسخ جميع scripts/references/models/assets/plugins/LUTs أو ملفات المشاريع التابعة للمصادر.
2. تراخيص المستودعات ليست بالضرورة تراخيص الأصول المضمنة أو الملفات الفرعية. Photoshop Expert يضيف attribution requirement إلى MIT. لم يظهر LICENSE في جذر Video EditAgent.
3. API prices والاشتراكات وحدود الاستخدام متغيرة؛ لا أذكر تكلفة غير مثبتة من ملف المهارة.
4. لا توجد أي مهارة مثبتة أو متصلة تلقائياً داخل ChatGPT. CLI/Desktop/API/MCP يحتاج الأدوات والحسابات وصلاحيات خارجية.
5. لم أشغل أي سكربت أو أنتج/حررت/نشرت وسيطاً في هذه الجولة.

