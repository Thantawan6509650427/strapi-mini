# 🚀 Getting started with Strapi CS360

## `strapi  คืออะไร`

วัตถุประสงค์หลักของ Strapi
เป็นระบบจัดการเนื้อหาสำหรับการสร้าง API ที่มีความยืดหยุ่นและง่ายต่อการปรับแต่ง ถูกออกแบบมาเพื่อให้การสร้างและจัดการเนื้อหาของเว็บไซต์และแอปพลิเคชันเป็นไปอย่างราบรื่นและมีประสิทธิภาพ

กรณีการใช้งาน (Use Cases)
1. เว็บไซต์บริษัทหรือองค์กร: ใช้ Strapi เพื่อจัดการเนื้อหาของเว็บไซต์ เช่น บทความ, ข่าวสาร, และข้อมูลเกี่ยวกับผลิตภัณฑ์
2. แอปพลิเคชันมือถือ: ใช้ Strapi เป็น backend สำหรับแอปพลิเคชันมือถือ เพื่อให้ข้อมูลในแอปพลิเคชันสามารถจัดการได้จากแดชบอร์ด
3. ระบบการจัดการเนื้อหา (CMS): ใช้ Strapi เป็น CMS สำหรับเว็บไซต์ที่ต้องการการปรับแต่งที่สูงและการควบคุมเนื้อหาที่ง่าย
4. ระบบการจัดการผลิตภัณฑ์: ใช้ Strapi ในการจัดการข้อมูลผลิตภัณฑ์, สต๊อก, และคำสั่งซื้อในระบบ E-commerce

องค์ประกอบหลักของ Strapi
1. แดชบอร์ดผู้ดูแลระบบ (Admin Dashboard): อินเตอร์เฟซสำหรับการจัดการเนื้อหาและการตั้งค่าของระบบ
2. Content Types Builder: เครื่องมือที่ช่วยสร้างและปรับแต่งโครงสร้างของเนื้อหา
3. API Generator: สร้าง API แบบ RESTful หรือ GraphQL อัตโนมัติจากโครงสร้างเนื้อหา
4. Authentication and Permissions: ระบบการตรวจสอบสิทธิ์และการจัดการสิทธิ์ของผู้ใช้
5. Plugins: ส่วนเสริมที่ช่วยเพิ่มฟังก์ชันการทำงาน เช่น การอัพโหลดไฟล์, การจัดการ SEO, และอื่น ๆ
6. Database Connectors: รองรับการเชื่อมต่อกับฐานข้อมูลหลายประเภท เช่น MySQL เป็นต้น

## `วิธีการติดตั้งและใช้งาน strapi`

การติดตั้ง Strapi จาก CLI
1. Node.js: ใช้เวอร์ชัน Active LTS หรือ Maintenance LTS เท่านั้น (ปัจจุบัน v18 และ v20)
2. Node.js package manager: npm (v6 ขึ้นไป)/yarn
3. Python (หากใช้ฐานข้อมูล SQLite)
4. ฐานข้อมูลที่รองรับ:
    MySQL: 5.7.8 ขึ้นไป (แนะนำ 8.0)
    MariaDB: 10.3 ขึ้นไป (แนะนำ 10.6)
    PostgreSQL: 11.0 ขึ้นไป (แนะนำ 14.0)
    SQLite: 3 ขึ้นไป
    MongoDB: ไม่รองรับใน Strapi v4

### `develop`

Start your Strapi application with autoReload enabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-develop)

การสร้างโปรเจกต์ Strapi

1. เปิดterminalและใช้คำสั่ง
```
npx create-strapi-app@latest my-project
```
2. เลือกประเภทการติดตั้ง:

Quickstart (แนะนำ): ใช้ฐานข้อมูลเริ่มต้น (SQLite) และ เลือก Skip

การรัน Strapi
ใช้คำสั่งต่อไปนี้ในโฟลเดอร์โปรเจกต์
```
npm run develop
# or
yarn develop
```

### `start`

Start your Strapi application with autoReload disabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-start)

```
npm run start
# or
yarn start
```

## ไฟล์ .gitignore 
มีวัตถุประสงค์เพื่อกำหนดไฟล์และไดเรกทอรีที่ Git ควรเพิกเฉยเมื่อทำการ commit 
1. ป้องกันการติดตามไฟล์ที่ไม่ต้องการ: ไฟล์ที่มีการสร้างโดยอัตโนมัติ เช่น ไฟล์ลอกรหัสหรือไฟล์การตั้งค่าเฉพาะบุคคลที่ไม่ควรแชร์กับคนอื่น
2. ลดขนาด repository: โดยการไม่ติดตามไฟล์ที่มีขนาดใหญ่หรือข้อมูลที่ไม่จำเป็น เช่น ไฟล์ฐานข้อมูล
3. หลีกเลี่ยงปัญหาการรวมโค้ด: ป้องกันไม่ให้ไฟล์ที่อาจสร้างปัญหาหรือข้อขัดแย้งในการรวมโค้ดถูก commit ไปด้วย

เนื้อหาภายในไฟล์ .gitignore ของ Strapi

1. node_modules/ วัตถุประสงค์: ไฟล์ในโฟลเดอร์ node_modules ประกอบด้วยแพ็กเกจที่ติดตั้งโดย npm หรือ yarn และไม่ควร commit เพราะสามารถติดตั้งใหม่จาก package.json
2. .tmp/ และ .data/ วัตถุประสงค์: ไฟล์ในโฟลเดอร์เหล่านี้เป็นไฟล์ชั่วคราวที่ Strapi ใช้ระหว่างการทำงาน ซึ่งไม่จำเป็นต้องถูก commit
3. .vscode/ วัตถุประสงค์: ไฟล์การตั้งค่า IDE ที่เฉพาะเจาะจงต่อผู้ใช้ เช่น การตั้งค่า VSCode ควรเพิกเฉยเนื่องจากเป็นการตั้งค่าเฉพาะบุคคล
4. build/ วัตถุประสงค์: ไฟล์ในโฟลเดอร์นี้เป็นไฟล์ที่สร้างขึ้นโดยกระบวนการ build และสามารถสร้างใหม่ได้จาก source code

การปรับเปลี่ยนไฟล์ .gitignore 
1. เพิ่มไฟล์หรือไดเรกทอรีที่ควรเพิกเฉย
2. ลบไฟล์หรือไดเรกทอรีที่ควรติดตาม
เหตุผลในการปรับเปลี่ยน
1. การจัดการไฟล์ที่ดีขึ้น: เพื่อให้ repository สะอาดและมีประสิทธิภาพ
2. การควบคุมเวอร์ชัน: เพื่อให้แน่ใจว่าไฟล์ที่สำคัญและจำเป็นได้รับการติดตามอย่างถูกต้อง
3. การรักษาความปลอดภัย: ป้องกันข้อมูลสำคัญหรือไฟล์เฉพาะบุคคลจากการถูกแชร์โดยไม่ได้ตั้งใจ

## ⚙️ Deployment (การ Deploy ลง AWS)
1. สร้าง AWS EC2 Instance
2. ตั้งค่า Security Group ของ EC2 ในส่วน Inbound
Type: SSH, Protocol: TCP, Port Range: 22, Source: ::/0
Type: HTTP, Protocol: TCP, Port Range: 80, Source: 0.0.0.0/0, ::/0
Type: HTTPS, Protocol: TCP, Port Range: 443, Source: 0.0.0.0/0, ::/0
Custom TCP Rule, Protocol: TCP, Port Range: 1337, Source: 0.0.0.0/0
3. ติดตั้ง NodeJS ลงบน EC2
```
cd ~
sudo yum update
sudo yum install -y ca-certificates curl gnupg
sudo yum install nodejs -y
node -v 
npm -v
```
4. สร้างและเปลี่ยน npm default directory
```
cd ~
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'

# แก้ไขไฟล์ .profile
sudo nano ~/.profile

# ใส่คำสั่ง  
export PATH=~/.npm-global/bin:$PATH

# ออกจากคำสั่ง และอัพเดตข้อมูล
source ~/.profile
```
5. ติดตั้ง package ลงโปรเจกต์ในเครื่องของเรา
```
cd ที่อยู่โปรเจกต์ในEC2
yarn add pg
yarn add @strapi/provider-upload-aws-s3
```
6. แก้ไข config โปรเจกต์ที่ ./config/plugins.js ในเครื่องของเรา
```
module.exports = ({ env }) => ({
      upload: {
        config: {
          provider: 'aws-s3',
          providerOptions: {
            s3Options: {
              accessKeyId: env('AWS_ACCESS_KEY_ID'),
              secretAccessKey: env('AWS_ACCESS_SECRET'),
              region: env('AWS_REGION'),
              params: {
                Bucket: env('AWS_BUCKET_NAME'),
              },
            }
          },
          // These parameters could solve issues with ACL public-read access — see [this issue](https://github.com/strapi/strapi/issues/5868) for details
          actionOptions: {
            upload: {
              ACL: null
            },
            uploadStream: {
              ACL: null
            },
          }
        },
      }
    });
```
7. Push โปรเจกต์บนเครื่องขึ้น github
```
git add .
git commit -m 'ข้อความที่จะ commit'
git push
```
8. ทำการโคลนโปรเจกต์มาไว้ในเครื่อง EC2
```
cd ~
git clone https://github.com/ชื่อในgithub/ชื่อrepository.git
```

9. ติดตั้ง package ลงโปรเจกต์ในเครื่อง EC2
```
cd ที่อยู่โปรเจกต์ในEC2
# ติดตั้ง Dependencies
npm install 
# NODE_ENV=production npm run build
NODE_ENV=production npm run build
```
10. ติดตั้ง PM2 Runtime
```
npm install pm2@latest -g
```
11. แก้ไข ecosystem.config.js
```
# เริ่มต้น PM2 และสร้างไฟล์การกำหนดค่า ecosystem
pm2 init 
# แก้ไขไฟล์ ecosystem.config.js
sudo nano ecosystem.config.js

# โดยแก้ไขข้อมูลข้างในไฟล์ดังนี้
module.exports = {
  apps: [
    {
      name: 'ชื่อโปรเจกต์', 
      cwd: '/home/ec2-user/เส้นทางไปยังโปรเจกต์', 
      script: 'yarn', 
      args: 'start', 
      env: {
        APP_KEYS: 'Key จาก .env ในโปรเจกต์ที่รันบนเครื่องของเรา',
        API_TOKEN_SALT: 'Salt จาก .env ในโปรเจกต์ที่รันบนเครื่องของเรา',
        ADMIN_JWT_SECRET: 'Admin Secret จาก .env ในโปรเจกต์ที่รันบนเครื่องของเรา',
        JWT_SECRET: 'Secret จาก .env ในโปรเจกต์ที่รันบนเครื่องของเรา',
        NODE_ENV: 'production',
        DATABASE_CLIENT: 'sqlite',
        DATABASE_FILENAME: '.tmp/data.db'
      },
    },
  ],
};
```
12.  Start PM2 ให้เว็ปไซต์ทำงาน โดยจะเข้าถึงเว็ปไซต์ได้ที่ http://public-ipของec2:1337/
```
pm2 start ecosystem.config.js
```
13. ตั้งค่าให้ PM2 ทำงานทันทีเมื่อทำการเปิด EC2
```
cd ~
pm2 startup systemd
...
# หลังจากนั้น console จะพิมพ์คำสั่งมาให้ ทำการก็อปวางได้ เช่น
sudo env PATH=$PATH:/usr/bin /usr/lib/node_modules/pm2/bin/pm2 startup systemd -u your-name --hp /home/your-name
...
pm2 save
...
# reboot 1 รอบ
sudo reboot
```


Strapi gives you many possible deployment options for your project including [Strapi Cloud](https://cloud.strapi.io). Browse the [deployment section of the documentation](https://docs.strapi.io/dev-docs/deployment) to find the best solution for your use case.

## reference
- [Resource](https://docs.strapi.io/dev-docs/installation/cli)
- [Resource](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files)
- [How to Write a Good README](https://www.freecodecamp.org/news/how-to-write-a-good-readme-file/)

## 📚 Learn more

- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://strapi.io/blog) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.

---

<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>
