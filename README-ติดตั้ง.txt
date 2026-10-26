วิธีทำให้ระบบติดตั้งเป็นแอปบน Android / iOS ได้จริง (PWA)
=========================================================
ไฟล์ในโฟลเดอร์นี้คือ "เปลือกแอป" ที่ครอบหน้า Apps Script เดิมไว้ (ข้อมูลและการทำงานยังอยู่ที่ Apps Script เหมือนเดิม)
ต้องนำโฟลเดอร์นี้ไปโฮสต์บนเว็บ https สักที่ จากนั้นแจกลิงก์นั้นให้ผู้ใช้ติดตั้ง

ตัวเลือกที่ฟรีและง่ายที่สุด: GitHub Pages
 1) สมัคร/ล็อกอิน github.com → New repository (ชื่ออะไรก็ได้ เช่น ifd-shift) → Public
 2) กด "uploading an existing file" แล้วลากไฟล์ทั้งหมดในโฟลเดอร์นี้ขึ้นไป (index.html, manifest.webmanifest, sw.js และโฟลเดอร์ icons) → Commit
 3) Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save
 4) รอ 1-2 นาที จะได้ลิงก์ https://<ชื่อผู้ใช้>.github.io/ifd-shift/
(ทางเลือกอื่น: Netlify Drop, Cloudflare Pages — ลากโฟลเดอร์นี้ไปวางได้เลย)

ลิงก์ Apps Script ที่ฝังอยู่ใน index.html (บรรทัด iframe src=...) คือ
 https://script.google.com/macros/s/AKfycbxkaa9l7UBr9aC1jufNn33VuUs1r0_EvHUCRWczsFhv3tEhXD6kxNcP1PlebT4-eFYzcw/exec
ถ้า Deploy ใหม่เป็น "ลิงก์ใหม่" (New deployment) ให้แก้บรรทัดนั้น แต่ถ้าใช้ Manage deployments → Edit → New version ลิงก์เดิมไม่เปลี่ยน

วิธีติดตั้งบนมือถือ (ใช้ลิงก์ GitHub Pages ข้างบน)
 Android (Chrome): เปิดลิงก์ → เมนู ⋮ → "ติดตั้งแอป" → ติดตั้ง
 iPhone/iPad (Safari): เปิดลิงก์ → ปุ่มแชร์ → "เพิ่มไปยังหน้าจอโฮม" → เพิ่ม

หมายเหตุ
 - ต้องมีอินเทอร์เน็ตตอนใช้งานเสมอ (ข้อมูลอยู่บน Google Sheets)
 - ผู้ใช้ iOS ต้องล็อกอิน Admin ใหม่ได้ในบางครั้ง เพราะ Safari จำข้อมูลของหน้าที่ฝังไว้ได้จำกัด
 - ใน Code.gs มีการเพิ่ม meta สำหรับเปิดเต็มจอแล้ว ผู้ที่เพิ่มลิงก์ Apps Script ตรงๆ ลงหน้าจอโฮมจะได้เป็นทางลัดแบบเต็มจอเช่นกัน
