from pathlib import Path

html = r'''&lt;!DOCTYPE html&gt;

&lt;html lang="vi"&gt;

&lt;head&gt;

&lt;meta charset="UTF-8"&gt;

&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;

&lt;title&gt;beeback — Nature-Inspired Design&lt;/title&gt;

&lt;link rel="preconnect" href="<https://fonts.googleapis.com>"&gt;

&lt;link href="<https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@500;600;700&display=swap>" rel="stylesheet"&gt;

&lt;style&gt;

:root{--cream:#f7f0df;--paper:#fffaf0;--yellow:#e4b947;--gold:#b88725;--ink:#28271f;--olive:#626343;--line:#d8c99f;--muted:#777363}

\*{box-sizing:border-box}html{scroll-behavior:smooth;scroll-padding-top:85px}body{margin:0;background:var(--cream);color:var(--ink);font-family:"DM Sans",sans-serif}a{color:inherit;text-decoration:none}button{font:inherit;cursor:pointer}

nav{position:sticky;top:0;z-index:10;display:flex;align-items:center;justify-content:space-between;padding:16px 7%;background:rgba(247,240,223,.94);backdrop-filter:blur(12px);border-bottom:1px solid var(--line)}.logo{font:700 1.7rem "Playfair Display",serif;letter-spacing:-1px}.logo span{color:var(--gold)}.navlinks{display:flex;gap:25px;font-size:.8rem;font-weight:700;letter-spacing:.06em;text-transform:uppercase}.navlinks a:hover{color:var(--gold)}.menu-toggle{display:none;border:0;background:none;font-size:1.5rem}

section{padding:88px 7%;scroll-margin-top:70px}.eyebrow{font-size:.75rem;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);font-weight:700}h1,h2,h3{font-family:"Playfair Display",serif;font-weight:600;line-height:1.08}h1{font-size:clamp(3.4rem,8vw,7.5rem);margin:20px 0}h2{font-size:clamp(2.3rem,4.5vw,4.1rem);margin:12px 0 22px}h3{font-size:1.45rem}p{line-height:1.75;color:#615e51}

.hero{min-height:82vh;display:grid;grid-template-columns:1.05fr .95fr;align-items:center;gap:45px;padding-top:60px}.hero p{max-width:550px;font-size:1.08rem}.hero-actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:28px}.btn{display:inline-flex;align-items:center;justify-content:center;padding:14px 19px;border:1px solid var(--ink);font-weight:700;font-size:.8rem;transition:.2s}.btn.primary{background:var(--ink);color:var(--paper)}.btn:hover{transform:translateY(-3px);box-shadow:4px 4px 0 var(--yellow)}

.hero-art{position:relative;min-height:450px;display:grid;place-items:center}.sun{position:absolute;width:min(36vw,360px);aspect-ratio:1;border-radius:50%;background:var(--yellow);right:5%;top:5%}.backpack{position:relative;width:min(75%,360px);height:350px;border:3px solid var(--ink);border-radius:46% 46% 35% 35%;background:#b9a66b;transform:rotate(-5deg);box-shadow:18px 20px 0 rgba(40,39,31,.12);overflow:hidden}.backpack:before{content:"";position:absolute;left:18%;right:18%;top:12%;height:22%;border:3px solid var(--ink);border-radius:50% 50% 20% 20%;background:#d5c18b}.backpack:after{content:"";position:absolute;left:16%;right:16%;bottom:8%;height:38%;border:3px solid var(--ink);border-radius:15px 15px 30% 30%;background:#c9b578}.strap{position:absolute;z-index:2;top:20%;bottom:5%;width:23%;border:3px solid var(--ink);border-radius:40px;background:repeating-linear-gradient(60deg,#e8d69f 0 9px,#b88725 9px 12px)}.strap.left{left:12%;transform:rotate(8deg)}.strap.right{right:12%;transform:rotate(-8deg)}.honeycomb{position:absolute;z-index:3;left:30%;top:44%;width:40%;height:26%;background-color:#e6c45e;background-image:radial-gradient(circle at 50% 50%,transparent 55%,#28271f 57%,#28271f 63%,transparent 65%);background-size:34px 30px;border:2px solid var(--ink);border-radius:12px}.sticker{position:absolute;z-index:4;right:0;bottom:8%;background:var(--paper);border:1px solid var(--ink);padding:12px 15px;font:600 1rem "Playfair Display",serif;transform:rotate(5deg)}

.section-head{max-width:740px;margin-bottom:38px}.about-grid,.product-grid,.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:50px;align-items:center}.panel{background:var(--paper);border:1px solid var(--line);padding:30px}.quote{font:italic 1.5rem/1.5 "Playfair Display",serif;border-left:4px solid var(--yellow);padding-left:22px;color:var(--ink)}.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:24px}.stat{border-top:1px solid var(--line);padding-top:14px}.stat strong{display:block;font:600 1.4rem "Playfair Display",serif}.stat span{font-size:.78rem;color:var(--muted)}

.team-grid,.cards-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}.member{padding:22px;background:var(--paper);border:1px solid var(--line);min-height:190px}.avatar{width:55px;height:55px;display:grid;place-items:center;background:var(--yellow);border-radius:50%;font:700 1.2rem "Playfair Display",serif;margin-bottom:20px}.member h3{font-size:1.2rem;margin:0 0 8px}.member p{font-size:.85rem;margin:0}

.dark{background:#292d22;color:var(--paper)}.dark p{color:#d4d0bd}.dark .eyebrow{color:#e4c56b}.research-layout{display:grid;grid-template-columns:.8fr 1.2fr;gap:30px}.journal-visual{min-height:330px;background:linear-gradient(145deg,#e4c25f,#b68a2f);border:1px solid #96712d;display:flex;align-items:center;justify-content:center;overflow:hidden}.hive{width:230px;height:230px;display:grid;grid-template-columns:repeat(4,1fr);gap:5px;transform:rotate(-10deg)}.hive i{display:block;background:rgba(255,248,220,.4);border:2px solid #544625;clip-path:polygon(25% 0,75% 0,100% 50%,75% 100%,25% 100%,0 50%)}.journal-content{display:grid;gap:12px}.info-row{background:var(--paper);padding:19px 22px;border:1px solid var(--line)}.info-row h3{margin:0 0 7px;font-size:1.2rem}.info-row p{margin:0;font-size:.93rem}

.cards-grid{grid-template-columns:repeat(3,1fr)}.bio-card{border:1px solid var(--line);background:var(--paper);padding:24px;min-height:260px;display:flex;flex-direction:column;transition:.25s}.bio-card:hover{transform:translateY(-6px);box-shadow:7px 7px 0 var(--yellow)}.card-number{font-size:.75rem;color:var(--gold);letter-spacing:.15em;font-weight:700}.hex-icon{font-size:2.5rem;margin:20px 0 10px}.bio-card h3{margin:0 0 8px}.bio-card p{font-size:.9rem;flex:1}.text-button{background:none;border:0;border-bottom:1px solid var(--gold);padding:8px 0;align-self:flex-start;font-weight:700;color:var(--gold)}

.process-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:0}.step{padding:22px 18px;border-top:2px solid var(--yellow);position:relative}.step:before{content:"";position:absolute;top:-7px;left:18px;width:12px;height:12px;border-radius:50%;background:var(--yellow);border:2px solid #292d22}.step small{color:#e4c56b;font-weight:700;letter-spacing:.1em}.step h3{font-size:1.2rem;margin:17px 0 10px}.step p{font-size:.85rem}

.gallery{display:grid;grid-template-columns:repeat(3,1fr);gap:15px}.placeholder{min-height:220px;background:#e8ddbd;border:1px dashed #a8945d;display:flex;align-items:center;justify-content:center;text-align:center;padding:22px;color:#6c6246;cursor:pointer}.placeholder strong{display:block;font:600 1.25rem "Playfair Display",serif;margin-bottom:8px;color:#39372d}.materials{width:100%;border-collapse:collapse;background:var(--paper);margin-top:22px}.materials th,.materials td{text-align:left;padding:14px;border-bottom:1px solid var(--line)}.materials th{background:#e9d69c;font-size:.78rem;text-transform:uppercase;letter-spacing:.08em}.product-illustration{min-height:370px;background:var(--yellow);display:grid;place-items:center;position:relative;overflow:hidden}.product-illustration .backpack{transform:scale(.8) rotate(-4deg)}.product-copy ul{padding-left:20px;color:#615e51;line-height:1.9}

.contact-box{background:var(--paper);padding:25px;border:1px solid var(--line)}footer{padding:25px 7%;display:flex;justify-content:space-between;gap:15px;flex-wrap:wrap;border-top:1px solid var(--line);font-size:.8rem;color:var(--muted)}

.modal{display:none;position:fixed;inset:0;z-index:30;background:rgba(20,20,15,.72);padding:20px;align-items:center;justify-content:center}.modal.open{display:flex}.modal-box{max-width:600px;width:100%;background:var(--paper);padding:35px;position:relative;border:1px solid var(--yellow);max-height:85vh;overflow:auto}.modal-close{position:absolute;right:15px;top:12px;border:0;background:none;font-size:1.7rem}.reveal{opacity:0;transform:translateY(18px);transition:opacity .6s,transform .6s}.reveal.visible{opacity:1;transform:none}

@media(max-width:850px){.hero,.about-grid,.product-grid,.research-layout,.contact-grid{grid-template-columns:1fr}.hero-art{min-height:380px}.team-grid{grid-template-columns:repeat(2,1fr)}.process-grid{grid-template-columns:repeat(2,1fr);gap:15px}.cards-grid{grid-template-columns:repeat(2,1fr)}}

@media(max-width:600px){nav{padding:14px 5%}.menu-toggle{display:block}.navlinks{display:none;position:absolute;top:60px;left:0;right:0;background:var(--cream);padding:20px 7%;border-bottom:1px solid var(--line);flex-direction:column;gap:18px}.navlinks.open{display:flex}section{padding:62px 6%}.hero{padding-top:40px;min-height:auto}.hero-art{min-height:320px}.backpack{height:290px}.team-grid,.cards-grid,.gallery{grid-template-columns:1fr}.process-grid{grid-template-columns:1fr}.stats{grid-template-columns:1fr}.materials th,.materials td{padding:9px 6px;font-size:.8rem}.panel{padding:22px}}

&lt;/style&gt;

&lt;/head&gt;

&lt;body&gt;

&lt;nav&gt;

&lt;a class="logo" href="#home"&gt;bee&lt;span&gt;back&lt;/span&gt;.&lt;/a&gt;

&lt;button class="menu-toggle" aria-label="Mở menu" id="menuToggle"&gt;☰&lt;/button&gt;

&lt;div class="navlinks" id="navlinks"&gt;

&lt;a href="#about"&gt;Về nhóm&lt;/a&gt;&lt;a href="#research"&gt;Nghiên cứu&lt;/a&gt;&lt;a href="#cards"&gt;Biomimicry&lt;/a&gt;&lt;a href="#process"&gt;Quy trình&lt;/a&gt;&lt;a href="#product"&gt;Sản phẩm&lt;/a&gt;&lt;a href="#contact"&gt;Liên hệ&lt;/a&gt;

&lt;/div&gt;

&lt;/nav&gt;

&lt;main&gt;

&lt;section class="hero" id="home"&gt;

&lt;div class="reveal"&gt;&lt;div class="eyebrow"&gt;Nhóm 2 · Biomimicry Design Agency&lt;/div&gt;&lt;h1&gt;Nature has&lt;br&gt;&lt;span style="color:var(--gold)"&gt;a better&lt;/span&gt;&lt;br&gt;way.&lt;/h1&gt;

&lt;p&gt;beeback khám phá cấu trúc tổ ong để tìm ra cách thiết kế quai balo thông thoáng hơn — nhẹ nhàng hơn trên vai, dễ chịu hơn trong hành trình mỗi ngày.&lt;/p&gt;

&lt;div class="hero-actions"&gt;&lt;a class="btn primary" href="#product"&gt;KHÁM PHÁ SẢN PHẨM ↗&lt;/a&gt;&lt;a class="btn" href="#research"&gt;HÀNH TRÌNH NGHIÊN CỨU&lt;/a&gt;&lt;/div&gt;

&lt;/div&gt;

&lt;div class="hero-art reveal" aria-label="Minh họa ý tưởng balo lấy cảm hứng từ tổ ong"&gt;&lt;div class="sun"&gt;&lt;/div&gt;&lt;div class="backpack"&gt;&lt;div class="strap left"&gt;&lt;/div&gt;&lt;div class="strap right"&gt;&lt;/div&gt;&lt;div class="honeycomb"&gt;&lt;/div&gt;&lt;/div&gt;&lt;div class="sticker"&gt;Inspired by the hive&lt;br&gt;Est. Group 02&lt;/div&gt;&lt;/div&gt;

&lt;/section&gt;

&lt;section id="about"&gt;&lt;div class="about-grid"&gt;

&lt;div class="reveal"&gt;&lt;div class="eyebrow"&gt;01 / Our story&lt;/div&gt;&lt;h2&gt;Học từ thiên nhiên.&lt;br&gt;Thiết kế cho đời sống.&lt;/h2&gt;

&lt;p&gt;Chúng mình là &lt;b&gt;beeback — Nhóm 2&lt;/b&gt;, một nhóm thiết kế lấy cảm hứng từ thiên nhiên. Từ cấu trúc tổ ong, nhóm tìm hiểu cách những ô lục giác tạo nên một hệ thống có tổ chức, đồng thời dùng cảm hứng đó để phát triển ý tưởng cho quai balo.&lt;/p&gt;

&lt;p&gt;Dự án tập trung vào trải nghiệm thường gặp: quai balo tạo cảm giác nặng vai và vùng tiếp xúc dễ bị nóng, ẩm khi đeo lâu. beeback hướng đến một thiết kế có cấu trúc thông thoáng, hỗ trợ phân bố tiếp xúc và cải thiện sự thoải mái.&lt;/p&gt;

&lt;/div&gt;

&lt;div class="panel reveal"&gt;&lt;div class="eyebrow"&gt;Our belief / Niềm tin&lt;/div&gt;&lt;p class="quote"&gt;"We don't copy nature. We learn from the way it works."&lt;/p&gt;&lt;p&gt;"Chúng tôi không sao chép thiên nhiên. Chúng tôi học cách thiên nhiên vận hành."&lt;/p&gt;&lt;div class="stats"&gt;&lt;div class="stat"&gt;&lt;strong&gt;01&lt;/strong&gt;&lt;span&gt;Natural inspiration&lt;/span&gt;&lt;/div&gt;&lt;div class="stat"&gt;&lt;strong&gt;02&lt;/strong&gt;&lt;span&gt;Team project&lt;/span&gt;&lt;/div&gt;&lt;div class="stat"&gt;&lt;strong&gt;∞&lt;/strong&gt;&lt;span&gt;Ideas to explore&lt;/span&gt;&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;

&lt;/div&gt;&lt;/section&gt;

&lt;section style="background:#eee4ca" id="team"&gt;&lt;div class="section-head reveal"&gt;&lt;div class="eyebrow"&gt;02 / The people&lt;/div&gt;&lt;h2&gt;Meet the team.&lt;/h2&gt;&lt;p&gt;Những người cùng biến quan sát thiên nhiên thành ý tưởng thiết kế. Hãy thay tên và vai trò mẫu bằng thông tin thật của nhóm.&lt;/p&gt;&lt;/div&gt;

&lt;div class="team-grid"&gt;

&lt;article class="member reveal"&gt;&lt;div class="avatar"&gt;01&lt;/div&gt;&lt;h3&gt;Thành viên 01&lt;/h3&gt;&lt;p&gt;Trưởng nhóm · Điều phối tiến độ&lt;/p&gt;&lt;/article&gt;

&lt;article class="member reveal"&gt;&lt;div class="avatar"&gt;02&lt;/div&gt;&lt;h3&gt;Thành viên 02&lt;/h3&gt;&lt;p&gt;Nghiên cứu sinh học · Biomimicry Journal&lt;/p&gt;&lt;/article&gt;

&lt;article class="member reveal"&gt;&lt;div class="avatar"&gt;03&lt;/div&gt;&lt;h3&gt;Thành viên 03&lt;/h3&gt;&lt;p&gt;Thiết kế concept · Sketch&lt;/p&gt;&lt;/article&gt;

&lt;article class="member reveal"&gt;&lt;div class="avatar"&gt;04&lt;/div&gt;&lt;h3&gt;Thành viên 04&lt;/h3&gt;&lt;p&gt;Render · Website · Mô hình&lt;/p&gt;&lt;/article&gt;

&lt;/div&gt;

&lt;/section&gt;

&lt;section class="dark" id="research"&gt;&lt;div class="section-head reveal"&gt;&lt;div class="eyebrow"&gt;03 / Nature research&lt;/div&gt;&lt;h2&gt;Nature is our first designer.&lt;/h2&gt;&lt;p&gt;Quan sát sinh vật, hiểu cơ chế, rút ra nguyên lý và chuyển hóa thành hướng thiết kế. Nội dung dưới đây là bản khởi đầu — hãy bổ sung dữ liệu nghiên cứu thực tế của nhóm.&lt;/p&gt;&lt;/div&gt;

&lt;div class="research-layout"&gt;

&lt;div class="journal-visual reveal" aria-label="Minh họa cấu trúc tổ ong"&gt;&lt;div class="hive"&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;i&gt;&lt;/i&gt;&lt;/div&gt;&lt;/div&gt;

&lt;div class="journal-content"&gt;

&lt;article class="info-row reveal"&gt;&lt;h3&gt;01 · Observe / Quan sát&lt;/h3&gt;&lt;p&gt;Tổ ong được tạo thành từ các ô có dạng lục giác, sắp xếp sát nhau thành một cấu trúc có trật tự.&lt;/p&gt;&lt;/article&gt;

&lt;article class="info-row reveal"&gt;&lt;h3&gt;02 · Understand / Thấu hiểu&lt;/h3&gt;&lt;p&gt;Cấu trúc ô lục giác giúp sử dụng không gian hiệu quả và tạo nên một mạng lưới liên kết. Hiệu quả thực tế phụ thuộc vào vật liệu và cách cấu tạo.&lt;/p&gt;&lt;/article&gt;

&lt;article class="info-row reveal"&gt;&lt;h3&gt;03 · Principle / Nguyên lý&lt;/h3&gt;&lt;p&gt;Khám phá cấu trúc dạng ô, khoảng rỗng và cách phân bố vật liệu để phát triển một bề mặt có tổ chức.&lt;/p&gt;&lt;/article&gt;

&lt;article class="info-row reveal"&gt;&lt;h3&gt;04 · Apply / Ứng dụng&lt;/h3&gt;&lt;p&gt;Đề xuất thử nghiệm cấu trúc dạng tổ ong trên vùng quai tiếp xúc vai để tạo khoảng thoáng. Cần kiểm tra mẫu thực tế về độ êm, độ bền và khả năng thoát ẩm.&lt;/p&gt;&lt;/article&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/section&gt;

&lt;section id="cards"&gt;&lt;div class="section-head reveal"&gt;&lt;div class="eyebrow"&gt;04 / Biomimicry cards&lt;/div&gt;&lt;h2&gt;Small clues. Big ideas.&lt;/h2&gt;&lt;p&gt;Bấm vào từng thẻ để xem tóm tắt nguyên lý và hướng ứng dụng. Thay nội dung mẫu bằng thẻ nghiên cứu chính thức của nhóm.&lt;/p&gt;&lt;/div&gt;

&lt;div class="cards-grid"&gt;

&lt;article class="bio-card reveal"&gt;&lt;div class="card-number"&gt;CARD / 01&lt;/div&gt;&lt;div class="hex-icon"&gt;🐝&lt;/div&gt;&lt;h3&gt;Tổ ong · Honeycomb&lt;/h3&gt;&lt;p&gt;Cấu trúc ô lục giác và mạng lưới liên kết.&lt;/p&gt;&lt;button class="text-button" data-modal="honey"&gt;XEM CHI TIẾT ↗&lt;/button&gt;&lt;/article&gt;

&lt;article class="bio-card reveal"&gt;&lt;div class="card-number"&gt;CARD / 02&lt;/div&gt;&lt;div class="hex-icon"&gt;〰️&lt;/div&gt;&lt;h3&gt;Khoảng rỗng · Airflow&lt;/h3&gt;&lt;p&gt;Hướng nghiên cứu về khoảng thoáng và luồng không khí quanh vùng tiếp xúc.&lt;/p&gt;&lt;button class="text-button" data-modal="air"&gt;XEM HƯỚNG NGHIÊN CỨU ↗&lt;/button&gt;&lt;/article&gt;

&lt;article class="bio-card reveal"&gt;&lt;div class="card-number"&gt;CARD / 03&lt;/div&gt;&lt;div class="hex-icon"&gt;🎒&lt;/div&gt;&lt;h3&gt;Ứng dụng · Strap concept&lt;/h3&gt;&lt;p&gt;Đưa cấu trúc dạng ô vào ý tưởng quai balo, sau đó thử nghiệm và điều chỉnh.&lt;/p&gt;&lt;button class="text-button" data-modal="strap"&gt;XEM CONCEPT ↗&lt;/button&gt;&lt;/article&gt;

&lt;/div&gt;

&lt;/section&gt;

&lt;section style="background:#eee4ca" id="moodboard"&gt;&lt;div class="section-head reveal"&gt;&lt;div class="eyebrow"&gt;05 / Visual direction&lt;/div&gt;&lt;h2&gt;Moodboard & material language.&lt;/h2&gt;&lt;p&gt;Phong cách cổ điển với sắc vàng mật ong, màu kem giấy và tông nâu trầm. Thay các ô dưới đây bằng ảnh moodboard thật của nhóm.&lt;/p&gt;&lt;/div&gt;

&lt;div class="gallery"&gt;

&lt;div class="placeholder reveal" data-modal="mood1"&gt;&lt;div&gt;&lt;strong&gt;01 / Honey gold&lt;/strong&gt;Vàng mật ong · màu chủ đạo&lt;/div&gt;&lt;/div&gt;

&lt;div class="placeholder reveal" data-modal="mood2"&gt;&lt;div&gt;&lt;strong&gt;02 / Hexagonal forms&lt;/strong&gt;Cấu trúc tổ ong · hình khối&lt;/div&gt;&lt;/div&gt;

&lt;div class="placeholder reveal" data-modal="mood3"&gt;&lt;div&gt;&lt;strong&gt;03 / Natural texture&lt;/strong&gt;Chất liệu · bề mặt · cảm giác&lt;/div&gt;&lt;/div&gt;

&lt;/div&gt;

&lt;/section&gt;

&lt;section id="process"&gt;&lt;div class="section-head reveal"&gt;&lt;div class="eyebrow"&gt;06 / Design process&lt;/div&gt;&lt;h2&gt;From nature to product.&lt;/h2&gt;&lt;p&gt;Hành trình thiết kế được trình bày theo trình tự để người xem hiểu cách nhóm phát triển ý tưởng.&lt;/p&gt;&lt;/div&gt;

&lt;div class="process-grid"&gt;

&lt;article class="step reveal"&gt;&lt;small&gt;STAGE 01&lt;/small&gt;&lt;h3&gt;Research&lt;/h3&gt;&lt;p&gt;Nghiên cứu tổ ong và vấn đề quai balo nóng, ẩm, tạo áp lực lên vai.&lt;/p&gt;&lt;/article&gt;

&lt;article class="step reveal"&gt;&lt;small&gt;STAGE 02&lt;/small&gt;&lt;h3&gt;Principle&lt;/h3&gt;&lt;p&gt;Rút ra hướng nghiên cứu về cấu trúc ô và khoảng thoáng.&lt;/p&gt;&lt;/article&gt;

&lt;article class="step reveal"&gt;&lt;small&gt;STAGE 03&lt;/small&gt;&lt;h3&gt;Sketch&lt;/h3&gt;&lt;p&gt;Phác thảo hình dáng quai, tỷ lệ và vị trí cấu trúc thông thoáng.&lt;/p&gt;&lt;/article&gt;

&lt;article class="step reveal"&gt;&lt;small&gt;STAGE 04&lt;/small&gt;&lt;h3&gt;AI Render&lt;/h3&gt;&lt;p&gt;Minh họa concept bằng hình ảnh AI; không thay thế mô hình thật.&lt;/p&gt;&lt;/article&gt;

&lt;article class="step reveal"&gt;&lt;small&gt;STAGE 05&lt;/small&gt;&lt;h3&gt;Prototype&lt;/h3&gt;&lt;p&gt;Chế tạo mô hình, đánh giá độ bền, độ êm và sự thông thoáng.&lt;/p&gt;&lt;/article&gt;

&lt;/div&gt;

&lt;/section&gt;

&lt;section style="background:#eee4ca" id="gallery"&gt;&lt;div class="section-head reveal"&gt;&lt;div class="eyebrow"&gt;07 / Project archive&lt;/div&gt;&lt;h2&gt;Sketches, renders & making.&lt;/h2&gt;&lt;p&gt;Các khung ảnh mẫu có thể bấm để xem hướng dẫn thay ảnh. Khi chỉnh code, bạn có thể thay mỗi khung bằng thẻ &lt;code&gt;&lt;img&gt;&lt;/code&gt;.&lt;/p&gt;&lt;/div&gt;

&lt;div class="gallery"&gt;

&lt;div class="placeholder reveal" data-modal="sketch"&gt;&lt;div&gt;&lt;strong&gt;✏️ Final Sketch&lt;/strong&gt;Thêm ảnh bản phác thảo đã chỉnh sửa&lt;/div&gt;&lt;/div&gt;

&lt;div class="placeholder reveal" data-modal="render"&gt;&lt;div&gt;&lt;strong&gt;✦ AI Concept Render&lt;/strong&gt;Thêm ảnh render AI và chú thích&lt;/div&gt;&lt;/div&gt;

&lt;div class="placeholder reveal" data-modal="model"&gt;&lt;div&gt;&lt;strong&gt;▣ Physical Prototype&lt;/strong&gt;Thêm ảnh/video mô hình thật&lt;/div&gt;&lt;/div&gt;

&lt;/div&gt;

&lt;h3 style="margin-top:42px"&gt;Material plan / Dự trù vật liệu&lt;/h3&gt;

&lt;div style="overflow-x:auto"&gt;&lt;table class="materials"&gt;&lt;thead&gt;&lt;tr&gt;&lt;th&gt;Vật liệu / Material&lt;/th&gt;&lt;th&gt;Số lượng&lt;/th&gt;&lt;th&gt;Công dụng / Purpose&lt;/th&gt;&lt;/tr&gt;&lt;/thead&gt;&lt;tbody&gt;

&lt;tr&gt;&lt;td&gt;Vật liệu 01 — cần bổ sung&lt;/td&gt;&lt;td&gt;—&lt;/td&gt;&lt;td&gt;Phần khung / cấu trúc&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;Vật liệu 02 — cần bổ sung&lt;/td&gt;&lt;td&gt;—&lt;/td&gt;&lt;td&gt;Bề mặt / lớp đệm&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;Vật liệu 03 — cần bổ sung&lt;/td&gt;&lt;td&gt;—&lt;/td&gt;&lt;td&gt;Liên kết / hoàn thiện&lt;/td&gt;&lt;/tr&gt;

&lt;/tbody&gt;&lt;/table&gt;&lt;/div&gt;

&lt;/section&gt;

&lt;section id="product"&gt;&lt;div class="product-grid"&gt;

&lt;div class="product-illustration reveal"&gt;&lt;div class="backpack"&gt;&lt;div class="strap left"&gt;&lt;/div&gt;&lt;div class="strap right"&gt;&lt;/div&gt;&lt;div class="honeycomb"&gt;&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;

&lt;div class="product-copy reveal"&gt;&lt;div class="eyebrow"&gt;08 / Product concept&lt;/div&gt;&lt;h2&gt;beeback&lt;br&gt;Breathable Strap&lt;/h2&gt;&lt;p&gt;&lt;b&gt;Ý tưởng sản phẩm · Quai balo lấy cảm hứng từ tổ ong&lt;/b&gt;&lt;/p&gt;&lt;p&gt;Concept hướng đến việc cải thiện cảm giác khi đeo balo bằng cách nghiên cứu cấu trúc dạng ô và các khoảng thoáng ở vùng tiếp xúc với vai.&lt;/p&gt;

&lt;ul&gt;&lt;li&gt;&lt;b&gt;Biomimicry:&lt;/b&gt; cảm hứng từ cấu trúc tổ ong.&lt;/li&gt;&lt;li&gt;&lt;b&gt;Comfort:&lt;/b&gt; hướng đến phân bố tiếp xúc dễ chịu hơn.&lt;/li&gt;&lt;li&gt;&lt;b&gt;Ventilation:&lt;/b&gt; thử nghiệm khoảng thoáng để hỗ trợ lưu thông không khí.&lt;/li&gt;&lt;li&gt;&lt;b&gt;Prototype:&lt;/b&gt; cần kiểm tra bằng mô hình và trải nghiệm thực tế.&lt;/li&gt;&lt;/ul&gt;

&lt;button class="btn primary" data-modal="product"&gt;XEM THUYẾT MINH SẢN PHẨM ↗&lt;/button&gt;

&lt;/div&gt;

&lt;/div&gt;&lt;/section&gt;

&lt;section style="background:#eee4ca" id="contact"&gt;&lt;div class="contact-grid"&gt;

&lt;div class="reveal"&gt;&lt;div class="eyebrow"&gt;09 / Get in touch&lt;/div&gt;&lt;h2&gt;Let's design&lt;br&gt;with nature.&lt;/h2&gt;&lt;p&gt;Cảm ơn bạn đã khám phá hành trình của beeback. Các thông tin liên hệ dưới đây là chỗ trống để nhóm bổ sung trước khi nộp bài.&lt;/p&gt;&lt;/div&gt;

&lt;div class="contact-box reveal"&gt;&lt;p&gt;&lt;b&gt;Thương hiệu / Brand&lt;/b&gt;&lt;br&gt;beeback — Nhóm 2&lt;/p&gt;&lt;p&gt;&lt;b&gt;Email học tập / Contact email&lt;/b&gt;&lt;br&gt;&lt;a href="mailto:<yourteam@example.com>"&gt;<yourteam@example.com>&lt;/a&gt; &lt;small&gt;(hãy thay email thật)&lt;/small&gt;&lt;/p&gt;&lt;p&gt;&lt;b&gt;Lớp / Class&lt;/b&gt;&lt;br&gt;\[Bổ sung lớp\]&lt;/p&gt;&lt;p&gt;&lt;b&gt;Trường / School&lt;/b&gt;&lt;br&gt;\[Bổ sung tên trường\]&lt;/p&gt;&lt;p&gt;&lt;b&gt;Môn học / Course&lt;/b&gt;&lt;br&gt;\[Bổ sung tên môn học\]&lt;/p&gt;&lt;/div&gt;

&lt;/div&gt;&lt;/section&gt;

&lt;/main&gt;

&lt;footer&gt;&lt;a class="logo" href="#home"&gt;bee&lt;span&gt;back.&lt;/span&gt;&lt;/a&gt;&lt;span&gt;Nature-inspired design · Group 02&lt;/span&gt;&lt;span&gt;© 2026 beeback — Student project&lt;/span&gt;&lt;/footer&gt;

&lt;div class="modal" id="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle"&gt;&lt;div class="modal-box"&gt;&lt;button class="modal-close" id="modalClose" aria-label="Đóng"&gt;×&lt;/button&gt;&lt;div class="eyebrow"&gt;beeback / Project notes&lt;/div&gt;&lt;h2 id="modalTitle" style="font-size:2rem;margin-top:15px"&gt;Chi tiết&lt;/h2&gt;&lt;div id="modalBody"&gt;&lt;p&gt;Nội dung.&lt;/p&gt;&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;

&lt;script&gt;

const menuToggle=document.getElementById('menuToggle');

const navlinks=document.getElementById('navlinks');

menuToggle.addEventListener('click',()=>navlinks.classList.toggle('open'));

navlinks.querySelectorAll('a').forEach(a=>a.addEventListener('click',()=>navlinks.classList.remove('open')));

const details={

honey:{title:'Tổ ong · Honeycomb',body:'&lt;p&gt;&lt;b&gt;Nhận diện:&lt;/b&gt; Tổ ong do ong mật xây dựng; nếu dùng trong bài nộp, hãy bổ sung tên loài và nguồn nghiên cứu đã xác minh.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Đặc điểm:&lt;/b&gt; Các ô lục giác ghép sát nhau tạo thành cấu trúc có trật tự.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Cơ chế / nguyên lý:&lt;/b&gt; Hình học lục giác giúp phủ kín mặt phẳng với ít khe hở; hiệu quả chịu lực phụ thuộc vật liệu, độ dày và cách cấu tạo.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Ứng dụng:&lt;/b&gt; Thử nghiệm bề mặt dạng ô trên quai balo để tạo cấu trúc nhẹ và có khoảng thoáng. Cần kiểm chứng bằng mẫu thực tế.&lt;/p&gt;'},

air:{title:'Khoảng thoáng · Airflow',body:'&lt;p&gt;&lt;b&gt;Hướng nghiên cứu:&lt;/b&gt; Tìm hiểu cách hình dạng bề mặt, khoảng cách với cơ thể và lỗ thông khí ảnh hưởng đến lưu thông không khí.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Ứng dụng dự kiến:&lt;/b&gt; Bố trí các khoảng hở trên vùng tiếp xúc của quai balo. Không khẳng định hiệu quả giảm ẩm nếu chưa thử nghiệm.&lt;/p&gt;'},

strap:{title:'Quai balo · Strap concept',body:'&lt;p&gt;&lt;b&gt;Vấn đề:&lt;/b&gt; Quai balo có thể tạo cảm giác nặng vai và nóng ẩm khi đeo lâu.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Giải pháp đang phát triển:&lt;/b&gt; Kết hợp hình thái lấy cảm hứng từ tổ ong với lớp đệm và các khoảng thoáng.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Cần kiểm tra:&lt;/b&gt; Độ bền, khả năng chịu tải, độ êm, độ an toàn cạnh và hiệu quả thông khí.&lt;/p&gt;'},

mood1:{title:'Moodboard — Honey gold',body:'&lt;p&gt;Thay khung này bằng ảnh bảng màu hoặc ảnh cảm hứng màu vàng mật ong. Có thể dùng màu kem làm nền và nâu trầm cho chữ để giữ tinh thần cổ điển.&lt;/p&gt;'},

mood2:{title:'Moodboard — Hexagonal forms',body:'&lt;p&gt;Thêm ảnh cận cảnh cấu trúc tổ ong, các ô lục giác hoặc hình khối lặp lại. Ghi nguồn ảnh khi sử dụng tư liệu bên ngoài.&lt;/p&gt;'},

mood3:{title:'Moodboard — Natural texture',body:'&lt;p&gt;Thêm hình ảnh chất liệu và bề mặt mà nhóm muốn thử nghiệm. Ưu tiên ảnh vật liệu thật nếu đã có mẫu.&lt;/p&gt;'},

sketch:{title:'Sketch gallery',body:'&lt;p&gt;Thay khung này bằng ảnh sketch đã chỉnh sửa. Trong HTML, tìm phần &lt;code&gt;id="gallery"&lt;/code&gt; và thay placeholder bằng thẻ ảnh, ví dụ: &lt;code&gt;&lt;img src="images/final-sketch.jpg" alt="Bản phác thảo cuối"&gt;&lt;/code&gt;.&lt;/p&gt;'},

render:{title:'AI concept render',body:'&lt;p&gt;Thêm ảnh render AI, kèm chú thích "AI concept visualization". Đây là hình minh họa ý tưởng, không phải bằng chứng mô hình đã chế tạo.&lt;/p&gt;'},

model:{title:'Physical prototype',body:'&lt;p&gt;Thêm ảnh hoặc video mô hình nhóm thực sự đã chế tạo. Nên chụp nhiều góc và chú thích phần nào áp dụng nguyên lý tổ ong.&lt;/p&gt;'},

product:{title:'beeback Breathable Strap',body:'&lt;p&gt;&lt;b&gt;Vấn đề:&lt;/b&gt; Vai balo nặng và vùng tiếp xúc có thể nóng, ẩm.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Cảm hứng:&lt;/b&gt; Cấu trúc tổ ong.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Hướng thiết kế:&lt;/b&gt; Khai thác hình thái dạng ô và các khoảng thoáng trên quai balo.&lt;/p&gt;&lt;p&gt;&lt;b&gt;Đánh giá:&lt;/b&gt; Kiểm tra độ bền, phân bố áp lực, độ thoải mái và lưu thông không khí trên nguyên mẫu. Hãy bổ sung ảnh mô hình và kết quả thử nghiệm của nhóm.&lt;/p&gt;'}

};

const modal=document.getElementById('modal'),modalTitle=document.getElementById('modalTitle'),modalBody=document.getElementById('modalBody');

function openModal(key){const item=details\[key\];if(!item)return;modalTitle.textContent=item.title;modalBody.innerHTML=item.body;modal.classList.add('open');document.body.style.overflow='hidden'}

function closeModal(){modal.classList.remove('open');document.body.style.overflow=''}

document.querySelectorAll('\[data-modal\]').forEach(el=>el.addEventListener('click',()=>openModal(el.dataset.modal)));

document.getElementById('modalClose').addEventListener('click',closeModal);

modal.addEventListener('click',e=>{if(e.target===modal)closeModal()});

document.addEventListener('keydown',e=>{if(e.key==='Escape')closeModal()});

const observer=new IntersectionObserver(entries=>entries.forEach(entry=>{if(entry.isIntersecting){entry.target.classList.add('visible');observer.unobserve(entry.target)}}),{threshold:.12});

document.querySelectorAll('.reveal').forEach(el=>observer.observe(el));

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;'''

path = Path("/mnt/data/beeback_website.html")

path.write_text(html, encoding="utf-8")

print(f"Đã tạo website: {path} ({len(html):,} ký tự)")