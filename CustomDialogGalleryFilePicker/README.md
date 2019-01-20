## Instalasi


* jangan lupa tambahkan izin membaca file di AndroidManifest.xml

```
	...
    	<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
	...

```


* tambahkan kedalam build.gradle : 

```

	allprojects {
		repositories {
			...
			maven { url "https://dl.bintray.com/renosyah/CustomDialogGalleryFilePicker" }
		}
	}

```


* tambahkan kedalam app.gradle : 

```

	dependencies {
		...
		implementation 'com.github.renosyah:CustomDialogGalleryFilePicker:1.7'
	
	}

```

* untuk penggunaan berikut adalah contohnya : 

```

CustomDialogGalleryFilePicker dialog = CustomDialogGalleryFilePicker(this);
	dialog.SetFullScreenActivity(true);
        dialog.SetIndonesian();
	dialog.SetOnShowDialog(new ShowDialog.OnShowMyFileListener() {
            	@Override
            	public void OnChoosedFile(String filename, File file) {

			// tempatkan kode anda disini untuk mengelola file setelah dipilih

            		}
        	});

	dialog.ShowPickupActivity();

```

* pengaturan untuk bahasa indonesia/inggris dan jendela activity :

```

	dialog.SetFullScreenActivity(true); 
	// apakah mau activity fullscreen atau tidak

        dialog.SetIndonesian(); 
	//mengubah seluruh kalimat menjadi bahasa indonesia

 	dialog.SetEnglish(); 
	//mengubah seluruh kalimat menjadi bahasa inggris


```


* dialog dan activity dapat di sesuaikan warnanya :

```

	int CustomColor = ResourcesCompat.getColor(this.getResources(), R.color.colorPrimaryDark,null);
	// persiapkan warna yg ingin digunakan	

	dialog.SetTheme(CustomColor);
	// set kedalam dialog


	dialog.ShowPickupActivity();
	// tampilkan

```


* dialog atau activity dapat dipilih sesuai kebutuhan : 
```

	dialog.ShowDialog(); 
	// untuk dialog namun hanya mengakses gambar

	dialog.ShowPickupActivity();
	 // untuk activity dapat mengakses gambar,musik,video dan lainya


```