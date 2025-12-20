<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>قياسات زيوت السيارات</title>
<style>
body{font-family:tahoma;direction:rtl;background:#f2f2f2;padding:20px}
h1{color:#003366}
input,select,button{padding:8px;margin:5px}
table{width:100%;background:#fff;border-collapse:collapse;margin-top:20px}
th,td{border:1px solid #aaa;padding:10px;text-align:center}
.good{color:green}
.mid{color:orange}
.bad{color:red}
</style>
</head>
<body>

<h1>موقع قياسات زيوت السيارات</h1>

<!-- إدخال البيانات -->
<input id="car" placeholder="اسم السيارة">

<select id="oil">
  <option value="">اختر نوع الزيت</option>
  <option>5W-30</option>
  <option>5W-40</option>
  <option>10W-30</option>
  <option>10W-40</option>
  <option>15W-40</option>
</select>

<input id="oxi" type="number" placeholder="الأكسدة (%)">

<button onclick="add()">إضافة</button>

<!-- الجدول -->
<table>
<tr>
<th>السيارة</th>
<th>نوع الزيت</th>
<th>الأكسدة</th>
<th>الحالة</th>
</tr>
<tbody id="rows"></tbody>
</table>

<script>
let data = [];

function status(o){
 if(o < 20) return "<span class='good'>جيد</span>";
 if(o < 35) return "<span class='mid'>متوسط</span>";
 return "<span class='bad'>تغيير الزيت</span>";
}

function add(){
 if(car.value=="" || oil.value=="" || oxi.value=="") return;

 data.push({
  car: car.value,
  oil: oil.value,
  oxi: Number(oxi.value)
 });

 car.value="";
 oil.value="";
 oxi.value="";

 render();
}

function render(){
 rows.innerHTML="";
 data.forEach(d=>{
  rows.innerHTML += `
   <tr>
    <td>${d.car}</td>
    <td>${d.oil}</td>
    <td>${d.oxi}%</td>
    <td>${status(d.oxi)}</td>
   </tr>
  `;
 });
}
</script>

</body>
</html>

