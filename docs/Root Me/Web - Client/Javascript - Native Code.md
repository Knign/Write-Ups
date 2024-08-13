---
custom_edit_url: null
sidebar_position: 7
---

![1](https://github.com/Kunull/Write-ups/assets/110326359/2c98bf17-4cc6-40d6-b292-ebc5de7add60)

The website prompts us to enter a password.

Let's check the source code.

![2](https://github.com/Kunull/Write-ups/assets/110326359/745f1dc5-77fc-416e-854f-e2c6d64416a6)

If we replace the last pair of brackets, to `toString()`, we can see the deobfuscated Javascript.

![3](https://github.com/Kunull/Write-ups/assets/110326359/ec409420-00ef-4359-bfdb-82feeedd334f)

```js
function anonymous() 
{
	a=prompt('Entrez le mot de passe');
	if(a=='toto123lol'){
		alert('bravo');
	}else{
		alert('fail...');
	}
}
```

## Password
```
toto123lol
```
