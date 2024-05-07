kotlin
// MainActivity.kt

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import kotlinx.android.synthetic.main.activity_main.*

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        button.setOnClickListener {
            val intent = Intent(this, SecondActivity::class.java)
            intent.putExtra("param1", editText1.text.toString())
            intent.putExtra("param2", editText2.text.toString())
            intent.putExtra("param3", editText3.text.toString())
            intent.putExtra("param4", editText4.text.toString())
            intent.putExtra("param5", editText5.text.toString())
            startActivity(intent)
        }
    }
}


kotlin
//SecondActivity.kt

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import kotlinx.android.synthetic.main.activity_second.*

class SecondActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_second)

        val param1 = intent.getStringExtra("param1")
        val param2 = intent.getStringExtra("param2")
        val param3 = intent.getStringExtra("param3")
        val param4 = intent.getStringExtra("param4")
        val param5 = intent.getStringExtra("param5")

        textView.text = "Param 1: $param1\nParam 2: $param2\nParam 3: $param3\nParam 4: $param4\nParam 5: $param5"

        backButton.setOnClickListener {
            finish()
        }
    }
}
