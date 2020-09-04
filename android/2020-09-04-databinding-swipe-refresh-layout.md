## XML에서 SwipeRefreshLayout의 이벤트 받기(DataBinding)

XML에서 SRL의 이벤트를 받을 수 있는 방법은 구글링하면 수업이 나온다. 아래와 같이 작성할 수 있다.

```xml
<androidx.swiperefreshlayout.widget.SwipeRefreshLayout
	...
  app:onRefreshListener="@{viewModel::onRefresh}"
  app:refreshing="@{viewModel.isLoading}">
  <RecyclerView
		...
	/>
</androidx.swiperefreshlayout.widget.SwipeRefreshLayout>
```



가끔.. 아래와 같이 작성하여 신경질나는 DataBinding Error를 보기도 한다.(XXXXX)

```xml
<androidx.swiperefreshlayout.widget.SwipeRefreshLayout
	...
  app:onRefreshListener="@{() -> viewModel.onRefresh()}"//here </androidx.swiperefreshlayout.widget.SwipeRefreshLayout>
  app:refreshing="@{viewModel.isLoading}">
  <RecyclerView
		...
	/>
</androidx.swiperefreshlayout.widget.SwipeRefreshLayout>
```

