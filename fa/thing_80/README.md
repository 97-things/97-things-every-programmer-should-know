# در تست نرم‌افزار فقط رفتار مورد انتظار را بسنجید

یکی از دام‌هایی که دولوپرها در حین تست نرم‌افزار در آن گرفتار می‌شوند این است که بر این باورند آنچه نرم‌افزار انجام می‌دهد دقیقاً همان تسکی است که قصد تست آن را دارند. گرچه در ظاهر چنین چیزی اصلاً دام تلقی نمی‌شود اما اگر کمی بیشتر این موضوع را بشکافیم، منظور واضح‌تر بیان گردد: یک اشتباه رایج در فرایند تست نرم‌افزار این است که تست را برای خصوصیات جانبی نسخهٔ مد نظر نرم‌افزار نوشت و این در حالی است چنین خصوصیاتی جانبی بوده و خیلی سنخیتی با رفتاری از نرم‌افزار که قصد سنجش آن را داریم ندارند!

در چنین شرایطی، یعنی زمانی‌ که تست‌ها به گونه‌ای نوشته می‌شوند که با برخی خصوصیات جانبی نرم‌افزار هماهنگ شده باشند، اعمال تغییرات روی بخش‌هایی از نرم‌افزار که مرتبط با رفتاری است که قرار آن را تست کنیم، منجر به شکست تست می‌شود. در چنین شرایطی، دولوپرها معمولاً یا دست به ریفکتورینگ کد می‌زنند و یا تست را مجدد می‌نویسند که چنین کاری اوضاع را خراب‌تر می‌کند بلکه توصیه می‌شود مشکل ریشه‌ای حل گردد.

برای روشن‌تر شدن این مسأله مثالی می‌زنیم. اگر تستی بنویسیم که علاوه بر سنجش رفتار نرم‌افزار، مثلاً جایگاه قرارگیری اِلِمان‌های روی صفحه را نیز بسنجد، اگر به هر دلیلی تغییری در رابط کاربری بدهیم و سپس نرم‌افزار را تست کنیم، تست ما با شکست مواجه می‌شود و این در حالی است که مد نظر قرار دادن چنین مسائل جانبی و به نوعی حاشیه‌ای، صرفاً به پیچیده‌تر کردن تست‌ها منجر شده و احتمال بروز شکست آنها را بیشتر خواهد کرد.

با این تفاسیر، توصیه می‌شود که در حین نوشتن Unit Test، صرفاً رفتاری که از نرم‌افزار یا اپلیکیشن انتظار داریم را تست کنیم نه مسائل حاشیه‌ای که عملاً تغییری در رفتار اپلیکیشن ایجاد نمی‌کنند.