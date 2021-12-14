# AlertDialog-Kotlin
Alert Dialog Kotlin

MainActivity.kt file

      val dialog = AlertDialog.Builder(requireContext)
            dialog.setMessage("Do you really want to delete?")
            dialog.setPositiveButton("Yes", DialogInterface.OnClickListener { dialog, which ->
                db.collection("bestofmonth").document(listBom[position].id).delete()
                    .addOnCompleteListener {
                        if (it.isSuccessful) {
                            Toast.makeText(
                                requireContext,
                                "Wallpaper Deleted Successfully",
                                Toast.LENGTH_SHORT
                            ).show()
                        } else {
                            Toast.makeText(
                                requireContext,
                                "" + it.exception?.localizedMessage,
                                Toast.LENGTH_SHORT
                            ).show()
                        }
                    }
                dialog.dismiss()
            })
            dialog.setNegativeButton("No", DialogInterface.OnClickListener{
                dialog, which ->
                dialog.dismiss()
            })

            dialog.show()
