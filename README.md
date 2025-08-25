<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2487.4">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica; min-height: 14.0px}
    span.s1 {font: 12.0px Thonburi}
    span.s2 {font: 12.0px 'Apple Color Emoji'}
  </style>
</head>
<body>
<p class="p1">&lt;!DOCTYPE html&gt;</p>
<p class="p1">&lt;html lang="th"&gt;</p>
<p class="p1">&lt;head&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;meta charset="UTF-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;title&gt;<span class="s1">ตะกร้าสินค้า</span>&lt;/title&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;style&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>body { font-family: Arial, sans-serif; background:#fdf6f0; padding:20px; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>h2 { text-align:center; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>table { width:100%; border-collapse:collapse; margin-top:20px; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>th, td { border:1px solid #ccc; padding:10px; text-align:center; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>th { background:#cdb4db; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>button { padding:5px 10px; border:none; border-radius:8px; cursor:pointer; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>button:hover { background:#ffafcc; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>.back { display:block; margin-top:20px; text-align:center; text-decoration:none; background:#a2d2ff; color:white; padding:10px 20px; border-radius:10px; }</p>
<p class="p1"><span class="Apple-converted-space">    </span>.back:hover { background:#779be7; }</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;/style&gt;</p>
<p class="p1">&lt;/head&gt;</p>
<p class="p1">&lt;body&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;h2&gt;<span class="s2">🛒</span> <span class="s1">ตะกร้าสินค้า</span>&lt;/h2&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;table&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;thead&gt;</p>
<p class="p1"><span class="Apple-converted-space">      </span>&lt;tr&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;th&gt;<span class="s1">สินค้า</span>&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;th&gt;<span class="s1">ราคา</span>&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;th&gt;<span class="s1">จำนวน</span>&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;th&gt;<span class="s1">รวม</span>&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;th&gt;<span class="s1">ลบ</span>&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">      </span>&lt;/tr&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/thead&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;tbody id="cart-items"&gt;&lt;/tbody&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;/table&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;h3 id="total"&gt;&lt;/h3&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;a href="index.html" class="back"&gt;<span class="s2">⬅️</span> <span class="s1">เลือกซื้อสินค้าต่อ</span>&lt;/a&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;script&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>let cart = JSON.parse(localStorage.getItem("cart")) || [];</p>
<p class="p1"><span class="Apple-converted-space">    </span>const tbody = document.getElementById("cart-items");</p>
<p class="p1"><span class="Apple-converted-space">    </span>let total = 0;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>function renderCart(){</p>
<p class="p1"><span class="Apple-converted-space">      </span>tbody.innerHTML = "";</p>
<p class="p1"><span class="Apple-converted-space">      </span>if(cart.length===0){</p>
<p class="p1"><span class="Apple-converted-space">        </span>tbody.innerHTML='&lt;tr&gt;&lt;td colspan="5"&gt;<span class="s1">ไม่มีสินค้าในตะกร้า</span>&lt;/td&gt;&lt;/tr&gt;';</p>
<p class="p1"><span class="Apple-converted-space">        </span>document.getElementById("total").innerText = "";</p>
<p class="p1"><span class="Apple-converted-space">        </span>return;</p>
<p class="p1"><span class="Apple-converted-space">      </span>}</p>
<p class="p1"><span class="Apple-converted-space">      </span>cart.forEach((item,index)=&gt;{</p>
<p class="p1"><span class="Apple-converted-space">        </span>const tr = document.createElement("tr");</p>
<p class="p1"><span class="Apple-converted-space">        </span>tr.innerHTML=`</p>
<p class="p1"><span class="Apple-converted-space">          </span>&lt;td&gt;${item.name}&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">          </span>&lt;td&gt;${item.price} <span class="s1">บาท</span>&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">          </span>&lt;td&gt;${item.quantity}&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">          </span>&lt;td&gt;${item.price*item.quantity} <span class="s1">บาท</span>&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">          </span>&lt;td&gt;&lt;button onclick="removeItem(${index})"&gt;<span class="s1">ลบ</span>&lt;/button&gt;&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>`;</p>
<p class="p1"><span class="Apple-converted-space">        </span>tbody.appendChild(tr);</p>
<p class="p1"><span class="Apple-converted-space">        </span>total += item.price*item.quantity;</p>
<p class="p1"><span class="Apple-converted-space">      </span>});</p>
<p class="p1"><span class="Apple-converted-space">      </span>document.getElementById("total").innerText = "<span class="s1">ยอดรวมทั้งหมด</span>: "+total+" <span class="s1">บาท</span>";</p>
<p class="p1"><span class="Apple-converted-space">    </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>function removeItem(index){</p>
<p class="p1"><span class="Apple-converted-space">      </span>cart.splice(index,1);</p>
<p class="p1"><span class="Apple-converted-space">      </span>localStorage.setItem("cart", JSON.stringify(cart));</p>
<p class="p1"><span class="Apple-converted-space">      </span>total=0;</p>
<p class="p1"><span class="Apple-converted-space">      </span>renderCart();</p>
<p class="p1"><span class="Apple-converted-space">    </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>renderCart();</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;/script&gt;</p>
<p class="p1">&lt;/body&gt;</p>
<p class="p1">&lt;/html&gt;</p>
</body>
</html>
