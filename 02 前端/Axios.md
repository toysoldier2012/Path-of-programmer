#todo 


```javascript
<script> 
function getInfo() { axios.get('/mvc/test').then(({data}) => { 
	document.getElementById('username').innerText = data.username 
	document.getElementById('password').innerText = data.password }) 
} 
</script>
```

```javascript
<script> 
function login() { 
	axios.post('/mvc/test', { 
		username: 'test', password: '123456' 
	}, {
		headers: { 
			'Content-Type': 'application/x-www-form-urlencoded' 
		} 
	}).then(({data}) => { 
		if(data.success) { alert('登录成功') } 
		else { alert('登录失败') } 
	}) 
} 
</script>
```