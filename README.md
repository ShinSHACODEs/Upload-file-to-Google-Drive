# ก่อนดำเนินงานใด ให้แน่ใจว่ามีไฟล์ script สำหรับโค้ด และใส่ไว้ใน Repositories
ตัวอย่างโปรเจค
![image](https://github.com/user-attachments/assets/3b683349-6593-41d8-8527-809327779fb9)

# เมื่อสร้างแล้ว ให้ทำการเข้า Google API Service หรือ Google Cloud
ให้ทำการ create new project รองรับไว้ก่อน
![image](https://github.com/user-attachments/assets/85f30b76-01b1-4fa1-9199-4a57af1d514d)

หลังจากนั้นเข้าเมนูตัวเลือก IAM and Admin
https://console.cloud.google.com/
ทำการ Select Project ที่ตั้งเอาไว้

![image](https://github.com/user-attachments/assets/1b2b6380-f0d1-4bbf-8062-bba4db16d7c5)
# สร้าง create service accout

กดไปตัวเลือกหน้า Key เพื่อสร้าง Keys สำหรับเอา ใส่ใน secrets
![image](https://github.com/user-attachments/assets/60ffefe7-13ef-4032-be4e-51e90df2b8f7)

หลังจากได้แล้วให้บันทึกและเก็บไฟล์ JSON ไว้


# สร้าง Create File ใหม่ใน Github สำหรับทำ .yml
       - name: Upload to Google Drive
         uses: mathisve/gdrive-upload-action@main
         with:
           filename: ./weatherdata.csv
           name: weatherdata.csv
           folderId: ${{ secrets.FOLDER_ID }}
           credentials: ${{ secrets.GDRIVE_SERVICE_ACCOUNT }}
           encoded: false
ตัวอย่างที่ได้ผล
FoldID: คือ URL ของ Folder ใน Google Drive
credentials: คือ Keys ประเภท JSON

# ให้ทำการ setting ใน folder ของ github ที่มีไฟล์ yml
สร้าง Secrets key ต่างโดยก็อปสิ่งจำเป็นทั้งหมดลงไปแยกไฟล์ตามชื่อ เป็นอันเสร็จ
![image](https://github.com/user-attachments/assets/d7e1e1ca-d809-4a88-bdef-768271a213c3)

