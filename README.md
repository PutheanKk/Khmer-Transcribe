# Khmer Subtitle AI — PWA (build APK via PWA Builder)

## ជំហានទី ១: Host ជា GitHub Pages (ដោយប្រើទូរស័ព្ទ)
1. បង្កើត repo ថ្មីលើ GitHub (ឬប្រើ repo ចាស់)
2. Upload ឯកសារទាំង ៤ (`index.html`, `manifest.json`, `sw.js`, folder `icons/`) ទៅ root របស់ repo
   - សម្រាប់ folder `icons/`: use "Add file → Create new file" ហើយវាយ path ពេញ
     `icons/icon-192.png` — ក៏ដោយ GitHub មិនអនុញ្ញាតឲ្យ upload binary (.png) តាមរបៀបនេះទេ
     ដូច្នេះប្រើ "Add file → Upload files" វិញ ហើយអូស/ជ្រើសទាំង ២ រូបភាព ដាក់ចូល folder icons (បង្កើត folder ដោយវាយ `icons/icon-192.png` ក្នុងឈ្មោះពេល upload)
3. ចូល **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main` / `(root)` → Save
4. រង់ចាំ ១-២ នាទី នឹងទទួល URL ដូចជា `https://yourname.github.io/repo-name/`

## ជំហានទី ២: Build APK ជាមួយ PWA Builder
1. ចូល **https://www.pwabuilder.com**
2. ដាក់ URL GitHub Pages របស់អ្នក ចូល box → ចុច **Start**
3. PWA Builder នឹងវិភាគ manifest.json ស្វ័យប្រវត្តិ (គួរឃើញពិន្ទុល្អ ព្រោះ manifest+icons+sw.js គ្រប់គ្រាន់ស្រាប់)
4. ចុច **Package for stores** → ជ្រើស **Android**
5. ដាក់ Package ID (ឧ. `com.example.khmersubtitle`) → Generate → ទាញយក `.zip`
6. ក្នុង zip នោះមាន `.apk` (ឬ `.aab`) → extract → ដំឡើងលើទូរស័ព្ទ (បើក "Install unknown apps" ជាមុន)

## ចំណុចសំខាន់
- **API Key exposure**: Gemini API key ត្រូវបញ្ចូលដោយផ្ទាល់ក្នុង app (មិនមាន backend) ដូច្នេះកុំចែក app នេះជាសាធារណៈដោយភ្ជាប់ key ជាមួយ — ប្រើសម្រាប់ខ្លួនឯងតែប៉ុណ្ណោះ។
- Key ត្រូវបានរក្សាទុកក្នុង localStorage លើទូរស័ព្ទ (មិនផ្ញើទៅណាក្រៅពី Google Gemini API ទេ)។
- វីដេអូវែងអាចត្រូវការពេល upload/processing យូរ។
- ប្តូរ model name `gemini-2.5-flash` ក្នុង `index.html` ប្រសិនបើ Google ប្តូរឈ្មោះជំនាន់ថ្មី។
