<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>قياسات زيوت السيارات</title>
<style>
body{font-family:tahoma;direction:rtl;background:#f2f2f2;padding:20px}
h1{color:#003366}
input,button{padding:8px;margin:5px}
table{width:100%;background:#fff;border-collapse:collapse;margin-top:20px}
th,td{border:1px solid #aaa;padding:10px;text-align:center}
.good{color:green}
.mid{color:orange}
.bad{color:red}
</style>
</head>
<body>

<h1>موقع قياسات زيوت السيارات</h1>

<input id="car" placeholder="اسم السيارة">
<input id="visc" placeholder="اللزوجة">
<input id="oxi" placeholder="الأكسدة (%)">
<button onclick="add()">إضافة</button>

<table>
<tr>
<th>السيارة</th>
<th>اللزوجة</th>
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
 let o = Number(oxi.value);
 data.push({c:car.value,v:visc.value,o:o});
 render();
}

function render(){
 rows.innerHTML = "";
 data.forEach(d=>{
  rows.innerHTML += `<tr>
  <td>${d.c}</td>
  <td>${d.v}</td>
  <td>${d.o}%</td>
  <td>${status(d.o)}</td>
  </tr>`;
 });
}
</script>

</body>
</html>

