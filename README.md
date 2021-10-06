# AppHash

/***************** strings.xml 


<resources>
	<string name="app_name">simplehash</string>
	<string name="action_exit">Salir</string>
	<string name="txt_title">Testear una función hash</string>
	<string name="edt_message">Ingresa tu mensaje</string>
	<string name="rdb_md">MD5</string>
	<string name="rdb_sha">SHA-1</string>
	<string name="txt_hash">Valor hash</string>

</resources>





/***************** dimens.xml 


<resources>
	<dimen name="fab_margin">16dp</dimen>
	<dimen name="title_sz">32sp</dimen>
	<dimen name="content_sz">18sp</dimen>
</resources>




/***************** colors.xml 


<?xml version="1.0" encoding="utf-8" ?>
<resources>
	<color name="colorPrimary">#006666</color>
	<color name="colorPrimaryDark">#80ccff</color>
	<color name="colorAccent">#00cccc</color>
</resources>




/***************** menu_main.xml 

<menu xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
tools:context="uttec.security.simplehash.MainActivity">

<item
android:id="@+id/action_exit"
android:orderInCategory="100"
android:title="Exit"
app:showAsAction="ifRoom"
/>
</menu>





/***************** activity_main.xml 

<?xml version="1.0" encoding="utf-8" ?>
<androidx.coordinatorlayout.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<com.google.android.material.appbar.AppBarLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:theme="@style/AppTheme.AppBarOverlay">

<androidx.appcompat.widget.Toolbar
android:id="@+id/toolbar"
android:layout_width="match_parent"
android:layout_height="?attr/actionBarSize"
android:background="?attr/colorPrimary"
app:popupTheme="@style/AppTheme.PopupOverlay"/>

</com.google.android.material.appbar.AppBarLayout>

<include layout="@layout/content_main"/>

<com.google.android.material.floatingactionbutton.FloatingActionButton
android:id="@+id/fab"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_gravity="bottom|end"
android:layout_margin="@dimen/fab_margin"
app:srcCompat="@android:drawable/ic_secure"/>
</androidx.coordinatorlayout.widget.CoordinatorLayout>







/***************** content_main.xml 


<?xml version="1.0" encoding="utf-8" ?>
<androidx.constraintLayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
app:layout_behavior="com.google.android.material.appbar.AppBarLayout$Scr"
tools:context=".MainActivity"
tools:showIn="@layout/activity_main">

<TextView
android:id="@+id/txtTitle"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:layout_marginLeft="16dp"
android:layout_marginTop="16dp"
android:layout_marginRight="16dp"
android:text="@string/txt_title"
android:textAlignment="center"
android:textSize="@dimen/title_sz"
app:layout_constraintBottom_toTopOf="@+id/edtMessage"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintTop_toTopOf="parent"/>

<EditText
android:id="@+id/edtMessage"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:layout_marginStart="@dimen/fab_margin"
android:layout_marginTop="@dimen/fab_margin"
android:layout_marginEnd="@dimen/fab_margin"
android:ems="10"
android:hint="@string/edt_message"
android:inputType="none"
android:textColor="@color/colorPrimaryDark"
android:textSize="@dimen/content_sz"
app:layout_constraintBottom_toTopOf="@+id/rdgFunction"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/txtTitle"/>

<RadioGroup
android:id="@+id/rdgFunction"
android:layout_width="0dp"
android:layout_height="wrap_content"
android:layout_marginTop="@dimen/fab_margin"
android:gravity="center_horizontal"
android:orientation="horizontal"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/edtMessage">

<RadioButton
android:id="@+id/rdbMD"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/rdb_md"
android:textSize="@dimen/content_sz"/>

<RadioButton
android:id="@+id/rdbSHA"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginStart="@dimen/fab_margin"
android:text="@string/rdb_sha"
android:textSize="@dimen/content_sz"/>
</RadioGroup>

<TextView
android:id="@+id/txvHash"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:layout_marginStart="@dimen/fab_margin"
android:layout_marginTop="32dp"
android:layout_marginEnd="@dimen/fab_margin"
android:text="@string/txt_hash"
android:textColor="@color/colorPrimary"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/rdgFunction"/>

<EditText
android:id="@+id/edtHash"
android:layout_width="0dp"
android:layout_height="wrap_content"
android:layout_marginStart="@dimen/fab_margin"
android:layout_marginEnd="@dimen/fab_margin"
android:ems="10"
android:gravity="start|top"
android:inputType="none|textMultiLine"
android:selectAllOnFocus="true"
android:textAligment="center"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/txvHash"/>

</androidx.constraintLayout.widget.ConstraintLayout>



/***************** MainActivity.java

package uttec.security.simplehash;

import android.os.Bundle;
import com.google.android.material.floatingactionbutton.FloatingActionButton;
import com.google.android.material.snackbar.Snackbar;
import androidx.appcompat.app.AppCompatActivity;
import androidx.appcompat.widget.Toolbar;

import android.view.View;
import android.view.Menu;
import android.view.MenuItem;
import android.widget.EditText;
import android.widget.RadioButton;

import java.math.BigInteger;
import java.nio.charset.StandardCharsets;
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;

public class MainActivity extends AppCompatActivity {
	private EditText edtMessage;
	private EditText edtHash;
	private RadioButton rdbMD;
	private RadioButton rdbSHA;

	public String getHexString(byte[] byteArray) {
	BigInteger number = new BigInteger (signum:1, byteArray);
	StringBuilder hexString = new StringBuilder(number.toString(radix:16));
	while (hexString.lenght() < 32)
	{
		hexString.insert(offset:0, c:'0');
	}
	return hexString.toString().toUpperCase();
}

public byte[] getHash (String message, int algorithm) {
	MessageDigest md = null;
	try {
	switch (algorithm) {
	case 1:
	md = MessageDigest.getInstance("MD5"); //128
	break;
	case 2:
	md = MessageDigest.getInstance("SHA-1"); //160
	break;
	default:
	md = MessageDigest.getInstance("MD5");
	break;
}
} catch (NoSuchAlgorithmException ex) {
	Snackbar.make(view:null, text:"Algoritmo Hash Desconocido", Snackbar.LENGHT_LONG).show();
}
return md.digest(message.getBytes(StandardCharsets.UTF_8));
}

public void printHash() {
	String clearMessage = edtMessage.getText().toString();
	int hashAlg = 0;
	if (rdbMD.isChecked()) hashAlg = 1; //MD5
	if (rdbSHA.isChecked()) hashAlg = 2; //SHA-1

	String hashedMessage = getHexString (getHash (clearMessage, hashAlg));
	edtHash.setText(hashedMessage);
}

@Override
protected void onCreate (Bundle savedInstanceState) {
	super.onCreate(savedInstanceState);
	setContentView(R.layout.activity_main);
	Toolbar toolbar = findViewById(R.id.toolbar);
	setSupportActionBar (toolbar);

	edtMessage = (EditText) findViewById(R.id.edtMessage);
	edtHash = (EditText) findViewById(R.id.edtHash);
	rdbMD = (RadioButton) findViewById(R.id.rdbMD);
	rdbSHA = (RadioButton) findViewById(R.id.rdbSHA);

	FloatingActionButton fab = findViewById(R.id.fab);
	fab.setOnClickListener(new View.OnClickListener() {
	@Override
	public void onClick(View view) {
	printHash();
}
});
}

@Override
public boolean onCreateOptionsMenu(Menu menu) {
	getMenuInflater().inflate(R.menu.menu_main, menu);
	return true;
}

@Override
public boolean onOptionsItemSelected(MenuItem item) {
	int id = item.getItemId();
	if (id == R.id.action_exit) {
	finish();
}
return super.onOptionsItemSelected(item);
}

} 
