# AlertDialog-Kotlin
Alert Dialog Kotlin

MainActivity.kt file

            val dialog = AlertDialog.Builder(requireContext)
            dialog.setTitle("Delete Wallpaper")
            dialog.setMessage("Do you really want to delete?")
            dialog.setPositiveButton("Yes", DialogInterface.OnClickListener { dialog, which ->
                            Toast.makeText(
                                requireContext,
                                "Hello",
                                Toast.LENGTH_SHORT
                            ).show()
                dialog.dismiss()
            })
            dialog.setNegativeButton("No", DialogInterface.OnClickListener{
                dialog, which ->
                dialog.dismiss()
            })

            dialog.show()
