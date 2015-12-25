<template>
	<div id="app">
		<h1>Hello,app</h1>
		<p>
			<a v-link="path : '/foo">Go to foo</a>
			<a v-link="path : '/bar">Go to Bar</a>
		</p>
		<!-- 路由外链 -->
	<rooter-view></rooter-view>
	</div>
</template>

<script type="text/ecmascript-6">
// 定义组件
var Foo = Vue.extend({
	template:'<p>This is foo !</p>'
})

var Bar = Vue.extend({
	template:'<p>This is Bar !</p>'
})

// 路由器需要一个根组件
var app = Vue.extend({})

// 创建一个路由实例
var router = new VueRouter()

// 定义路由规则，映射到一个组件上去  组件也可以使用 vue.extend({})
router.map({
	'/foo' : {
		compontent : Foo
	},
	'/bar' : {
		compontent : Bar
	}
})
</script>