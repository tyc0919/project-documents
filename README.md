# project-documents

## 系統建置教學
目前還沒整理，這邊先貼上我的筆記，至少設定都有在裡面

[筆記](https://hackmd.io/@m7FAYRfQTyesN05dgdeZEQ/r1LPP44ic)

套件、軟體安裝
- Vmware 
- Node.js
- Python

### Vmware

[虛擬機下載](https://drive.google.com/file/d/15pzjHaCGTkVl2LKIlygEYrH_krshfXPV/view?usp=sharing)

Import 我預先製作的虛擬機
打開Vmware，左上角有個File，點開再點Open，選擇Example.ovf
名字可以隨便取，然後對新增
點Power on this virtual machine就能打開

### Node.js
打開cmd輸入
```
npm install --global yarn
```

臨時前端測試:
1. 桌面開個資料夾，用cmd cd進去，然後打yarn create vite
2. 名字隨便打，選項都選vue
3. 覆蓋vite.config.js成以下內容
```javascript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  server: {
	  hmr: {
		  clientPort: 5173
	  }
  }
})
```


### Python
去官網安裝，不過應該大家都有

打開cmd，cd進入django資料夾(有requirement.txt的那個)然後輸入
```
python -m venv .venv
.venv\Scripts\activate
(.venv)pip install -r requirement.txt
```

剩下照原本後端的建置教學做

## 啟動伺服器

1. 啟動Vmware的Example虛擬機

2. 開啟兩個cmd
一個到frontend的資料夾輸入
```
yarn dev --host
```
另一個到django資料夾進入虛擬環境並啟動伺服器
```
.venv\Scripts\activate
(.venv)python manage.py runserver 0.0.0.0:8000
```

3. 打開瀏覽器無痕，輸入http://www.ace.project測試能不能到前端畫面


## 後端API可用方法
目前除了檢查登入資訊以外都沒有
 