## XML에서 SwipeRefreshLayout의 이벤트 받기(DataBinding)

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

