커스텀한 AlertDialog 배경을 바꾸고 싶을때..

AlertDialog에 setView 한 커스텀뷰의 Radius(Round)값을 바꾼다고 해서 AlertDialog의 Radius가 바뀌는 것은 아니다. AlertDialog에서 제공하는 뷰를 보이지 않게 해야만 커스텀뷰의 Radius가 제대로 보인다. AlertDialog의 기본뷰를 투명하게 주어, 온전히 커스텀한 뷰만 보이게 할 수 있다. 아래와 같이 배경을 투명으로 바꾸면 된다.

```kotlin
...
		override fun show(): AlertDialog {
        dialog = super.show()
        dialog.window?.setBackgroundDrawable(ColorDrawable(android.graphics.Color.TRANSPARENT))
        return dialog
    }
...
```



전체코드:

```kotlin
class WriterSelectDialog(context: Context) : AlertDialog.Builder(context) {
    private val binding by lazy {
        DialogWriterSelectBinding.inflate(LayoutInflater.from(context))
    }

    var clickListener: ((String) -> Unit)? = null

    init {
        setView(binding.root)
        binding.ivWriterSelectClose.setOnClickListener {
            dialog.dismiss()
        }

        binding.cvWriterSelectEmployeeBtn.setOnClickListener {
            clickListener?.invoke("A")
            dialog.dismiss()
        }

        binding.cvWriterSelectCustomerBtn.setOnClickListener {
            clickListener?.invoke("U")
            dialog.dismiss()
        }

    }

    private lateinit var dialog: AlertDialog

    override fun show(): AlertDialog {
        dialog = super.show()
        dialog.window?.setBackgroundDrawable(ColorDrawable(android.graphics.Color.TRANSPARENT))
        return dialog
    }


    companion object {
        const val EMPLOYEE: Int = 0
        const val CUSTOMER: Int = 1
    }
}
```

AlertDialog의 배경을 투명하게 구현하면서 새롭게 알게된 사실 하나!  안드로이드에서 제공하는 컬러값을 android.R.color.black 과 같은 리소스아이디 방식이 아닌 컬러값(`android.graphics.Color.TRANSPARENT`)을 바로 가져올 수 있다는것을 알게됐다.

```kotlin
ColorDrawable(android.graphics.Color.TRANSPARENT)
```

