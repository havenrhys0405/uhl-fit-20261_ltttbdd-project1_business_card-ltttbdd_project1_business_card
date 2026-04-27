<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5950e74c-d7f1-4b15-b7f5-5d2085d305ac" /># Lập trình trên thiết bị di động
## Dự án 1: Danh thiếp (Bussiness card)
- Commit code tại repo này
package com.example.test1

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.width
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.test1.ui.theme.Test1Theme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            Test1Theme {
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
                    BusinessCardApp(modifier = Modifier.padding(innerPadding))
                }
            }
        }
    }
}

@Composable
fun BusinessCardApp(modifier: Modifier = Modifier) {
    Column(
        modifier = modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Image(
            painter = painterResource(id = R.drawable.android_logo),
            contentDescription = null,
            modifier = Modifier
                .height(100.dp)
                .width(100.dp)
        )
        Text(
            text = "Lê Thị Vân",
            fontSize = 32.sp
        )
        Text(
            text = "Sinh viên Web",
            color = Color(0xFF3DDC84)
        )

        Spacer(modifier = Modifier.height(50.dp))

        Row {
            Text(text = "+84395913622")
        }
        Row {
            Text(text = "havenrhys0405@gmail.com")
        }
    }
}

@Preview(showBackground = true)
@Composable
fun BusinessCardPreview() {
    Test1Theme {
        BusinessCardApp()
    }
}
