---
title: 'Three Basic Components of Machine Learning Applications'
date: 2024-11-03
permalink: /posts/2024-11-03-three-components-ml/
---

Machine Learning Applications တွေမှာ အခြေခံ အားဖြင့် Components သုံးခုပါပါတယ်

1. Data.             2.Model.                3.Code

ဒီသုံးခုကတော့ ကိုယ့်ဘာသာ AI project တစ်ခု လုပ်တာပဲဖြစ်ဖြစ် MLOpsပိုင်းမှာပဲ ဖြစ်ဖြစ် အမြဲတမ်းပါနေမယ့် iterative process ဖြစ်ပါတယ်

1.Data တွေကို အရင်စုပြီး သူ့ရဲ့ class အလိုက် label အရင်တပ်ရပါတယ်
ဥပမာ ပန်းသီးပုံတစ်ပုံ ကို apple ဆိုပြီး စက်နားလည်အောင် label တပ်ပေးရတယ် 

2.အဲ့လို data တွေအားလုံးကို label တပ်ပြီးရင် Model တစ်ခုထွက်လာအောင် train ရပါတယ်

3.Model တစ်ခု ထွက်လာရင် Code အနေနဲ့ Software implementation တွေ git လိုကောင်မျိုးတွေ Model Deployment ပိုင်းတွေ စသဖြင့် လူတွေအသုံးပြုနိုင်အောင် သွားရတဲ့အပိုင်းတွေပါပါတယ်

ဒီ process သုံးခုက တစ်ခါလုပ်ရုံနဲ့မပြီးပါဘူး  ပုံထဲက မြားတွေကိုကြည့်မယ်ဆိုရင် iterative ဖြစ်နေတာကိုတွေ့ရမှာပါ
Phone companies တွေ သူတို့ Model ကို ထပ်ထပ် update လုပ်သလိုပဲ ကိုယ့်ရဲ့ Model ကိုလည်း Version update လုပ်ပေးရပါတယ်
အဲ့တာကြောင့် data အသစ်တွေ ထပ် collect လုပ် label အသစ်တွေထပ်တပ် Model ကိုပြန် train  Code အနေနဲ့ implementation တွေပြန်လုပ် ပြန် Deployment တွေလုပ်ရပါတယ်

ဒီ အခြေခံ  concept ကတော့ သိထားသင့်တဲ့အရာမလို့ ကိုယ့်ဘာသာလည်း note သဘောမျိုးနဲ့ မှတ်ထားချင်လို့ ရေးလိုက်ရခြင်းဖြစ်ပါတယ်

![Iterative MLOps loop]({{ "/images/data_model_code.jpg" | relative_url }})

p.s. ပုံက ဒီ ကနေယူထားတာပါ [inovex MLOps overview](https://www.inovex.de/en/our-services/data-science/mlops/)
အခုကျွန်တော် MLOps ပိုင်းကိုတော့ ဒီကနေ လေ့လာနေပါတယ်ဗျ 
[Alex Snow School YouTube Channel](https://youtube.com/@alexsnowschool?si=GJfPOdZHdV4hNeik)

---

