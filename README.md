<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>قياسات زيوت السيارات</title>
<style>
body{font-family:tahoma;direction:rtl;background:#f2f2f2;padding:20px}
h1{color:#003366}
select,input,button{padding:8px;margin:5px}
table{width:100%;background:#fff;border-collapse:collapse;margin-top:20px}
th,td{border:1px solid #aaa;padding:10px;text-align:center}
.good{color:green}
.mid{color:orange}
.bad{color:red}
</style>
</head>
<body>

<h1>قياسات زيوت السيارات</h1>

<select id="brand" onchange="loadModels()">
<option value="">اختر الشركة</option>
</select>

<select id="model" onchange="setOil()">
<option value="">اختر الموديل</option>
</select>

<input id="oil" readonly placeholder="نوع الزيت">
<input id="oxi" type="number" placeholder="الأكسدة (%)">

<button onclick="add()">إضافة</button>
<button onclick="exportCSV()">تصدير Excel</button>

<table>
<tr>
<th>الشركة</th>
<th>الموديل</th>
<th>الزيت</th>
<th>الأكسدة</th>
<th>الحالة</th>
</tr>
<tbody id="rows"></tbody>
</table>

<script>
const db = {
 "تويوتا":{
  "كورولا":"5W-30",
  "كامري":"5W-30",
  "لاندكروزر":"10W-40"
 },
 "نيسان":{
  "التيما":"5W-30",
  "باترول":"10W-40",
  "صني":"5W-30"
 },
 "هيونداي":{
  "إلنترا":"5W-30",
  "سوناتا":"5W-30"
 },
 "كيا":{
  "سيراتو":"5W-30",
  "سبورتاج":"5W-30"
 },
 "مرسيدس":{
  "C200":"5W-40",
  "E300":"5W-40"
 },
 "BMW":{
  "320":"5W-30",
  "520":"5W-30"
 }
};

Object.keys(db).forEach(b=>{
 let o=document.createElement("option");
 o.textContent=b; o.value=b;
 brand.appendChild(o);
});

function loadModels(){
 model.innerHTML="<option>اختر الموديل</option>";
 oil.value="";
 if(!brand.value) return;
 Object.keys(db[brand.value]).forEach(m=>{
  let o=document.createElement("option");
  o.textContent=m; o.value=m;
  model.appendChild(o);
 });
}

function setOil(){
 oil.value=db[brand.value][model.value]||"";
}

function status(o){
 if(o<20) return "جيد";
 if(o<35) return "متوسط";
 return "تغيير الزيت";
}

let data=[];
function add(){
 if(!brand.value||!model.value||!oxi.value) return;
 data.push([brand.value,model.value,oil.value,oxi.value,status(oxi.value)]);
 oxi.value="";
 render();
}

function render(){
 rows.innerHTML="";
 data.forEach(r=>{
  rows.innerHTML+=`<tr>${r.map(c=>`<td>${c}</td>`).join("")}</tr>`;
 });
}

function exportCSV(){
 let csv="الشركة,الموديل,الزيت,الأكسدة,الحالة\n";
 data.forEach(r=>csv+=r.join(",")+"\n");
 let a=document.createElement("a");
 a.href=URL.createObjectURL(new Blob([csv]));
 a.download="oil-report.csv";
 a.click();
}
</script>

</body>
</html>
