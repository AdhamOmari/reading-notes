# Read: 41 - Intent Filters

> Intent filter is a property that used in your app to allow other apps use a feature of your app.

> It is added in the manifest file if you want to use it

> Allowing Other Apps to Start Your Activity
> If your app can perform an action that might be useful   from another app, your app should be prepared to respond to action requests by specifying the appropriate intent filter in your activity.
 To allow other apps to start your activity in this way, you need to add an <intent-filter> element in your manifest file for the corresponding <activity> element.
 When your app is installed on a device, the system identifies your intent filters and adds the information to an internal catalog of intents supported by all installed apps. When an app calls startActivity() or startActivityForResult(), with an implicit intent, the system finds which activity (or activities) can respond to the intent.

 > Add an Intent Filter
 > In order to properly define which intents your activity can handle, each intent filter you add should be as specific as possible in terms of the type of action and data the activity accepts.

 Action:A string naming the action to perform. Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.

 Data: A description of the data associated with the intent.

 Category: Provides an additional way to characterize the activity handling the intent, usually related to the user gesture or location from which it's started

 > Handle the Intent in Your Activity
   In order to decide what action to take in your activity, you can read the Intent that was used to start it.

   As your activity starts, call getIntent() to retrieve the Intent that started the activity. You can do so at any time during the lifecycle of the activity, but you should generally do so during early callbacks such as onCreate() or onStart().

   > Return a Result
   If you want to return a result to the activity that invoked yours, simply call setResult() to specify the result code and result Intent. When your operation is done and the user should return to the original activity, call finish() to close (and destroy) your activity.

![alt](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAQYAAADBCAMAAAAace62AAABy1BMVEX///8BdroAcbheXl4DqJwAdLmitssAa7UBdrleX14Ab7cAc7kAcb0Abr8Abbbg6fOAq9L6yFEqgHwAbMG4zuQAaLT4+fiApMYnhoEcf3qksoBslp5ZjqX18fFUjsCQrMivtrZ0ncREh77OyWGfr4P/5ySrxeDG1+nw9PmixsLc5vHV1NXo6OgDZqcFV5E0g8AGQXIFX5ba0FbHx8cDjpeevdxTU1MCpZ2Xl5e+vr67vnCsrKw9mpOGo5GCgoLR0dH6xUGBq6CevpV2dnaVlZX+9ubN6eZ1brIAWa6StpqwyY6kpKSb0833hARmncwwg7R5pqP+8dn72ZI/s6mn2NNjvrY8iLIAjtC0wc9Ska6MspylwpO4z4r/vQD71IH957yagUtERET7z2zD5OF5xr8AZcWZuLbk7su71XJpYa3i63XJ2YNRgJvPq0zrtyPisjWtoGv84q4Cm6EChqgCfKhhWUl/cVX82Y6LeFBNVWO5kz13bFf968kEg5UFd5UGV4X75TGbmXv/7gdbc7mrc4ORgJz1hyd1i6/0gTfufUxel5OcwhfneGAAaGGz0F3cbnnidW3VqozS46a7mmfXZYvOWaGpzkLbuM61V6RrNLxfAAAZFElEQVR4nO2di2Max53Hd0eastpdlrV5JAqIk2kDK0DepgQCJQWBkGIEXdZBwkXyI4kUtakvaZ3rNU3jNGnSy7V2m/bSNO2fezP7Zh/AYhliqq+lARaEmQ+/md9vfjs7QxCXutSlLnWpS13qUpe61KX+jSX4VGzRH/jiJfBUwF1RSzkqjpGyi/7cF6tMlIaQxJqm1ARJJlpc9Ce/SGWjpKtc6m57Nppe9Ge/QKUgrhSuFqSBXnHIMIAhNSMBJE1q95ERcNh2lJeT3KI/+8VJMI2Bi/AAMgCiXyDxfJKhGZKhAVWMRmiGxochhbqECDD+ILPoT39hygQMOxcFIZqS0qIopVPFYlIU0xInpSU+JvIBKU3hpyCXjWYlRvsLenl6hwinNwQ6zWckPpQUJCEZ44sRdJOlIikiGYoSyWxS4EN8loPRlGD0G4Bf9Ke/MEVorceDASEbyvDpGzEpc0MoFiO8cCMpZnlBzN6IocMCnxZDAUYKcUajWDoMSEwyG42irzyUloRshC+mpXQ2RAlpgSL4EB3KFvmimOW4kCAkGc0elgwDhNgPMOhelC8GAnwaRUcAMDTNQQ4EUE/JkQGaRj0kjbxDIMDonmLJMFCKOSilKELl10OWVy6fNbjFRuMPLCeG6WNpSwmX0lPgkhpbOgxj+TD41/JhgGLSt1Jw6RoF+M413/oJvXTWAL7D4RElFmD0e+atm7jvgCXEAEg8soQkS6FuggIMbvwsYFgAzb4RmqXyJ0sXPuE6UT8PslTweNADbFwesIAEBwe9dpt19xEKuSXEwB4n5Ha7cb/RHrbbJ412Y0CK7QHZZD0iB3o5MQTvt2833x6044Nmoy2LyAzYdoIFGIPqHKGlUaACG9DyeQq6Fw/L8eawIfeORXkgxxssddDuAdkYVNvi6SVtFBB1BoAFuFuEgAk2WdRFsuhLJyml/pS9WSwpBlvbZ128g6Wk4HJ6igDwqcDSWQPu7/xrCaNIUv2GaY/SVfQypmRn078Hhompl2XDAFj/WkJPkXjBv+LAs2/I8CmR8idRWux5YYyB/d4PvudX3/0h62UNqSjAZ3utQbg1ADFLaJQQMnRgkWdEVQwvhH02ieCPfsh6WIOoBeB6Gn9qRRc4cUTDwKoJRgaI6MuhWHxCBlDo+6b0sYR1TIEqyP7IyxqKnOfckHHCZkHNvfaGdAxsu8lS1FBOMIBMNBmGAnLzJHwsA3dP4Y1BhKSTwUhsbn1u5H0X2CwMDM0mddCUm+2TXqN5+4Q6YXvwZCDLwP5Z1dIbg8fkGascuX+tAdGL6yY1DEH54KAZ7w3jzfgB226ztxPssBluNw9Y0tWyPTEIAeeLXTRKliIXHYcYGIJBud2G7TjbZuMN6nYQyO1GUBwC9+btiSEUML9ps6rOAavbSaFFYgiwQfDCC0o0xLIQ3SIPwA7jAD3E83/cP7GCwdVThAxr8O0pFmoN//nue3fuvMCOfiAG2D8itFRtnKdAGHx6CksuZ4EYgr+4c+cH33s77E9vy+MahSaaMevKMAYRZGgWBtB80UL7hl/e+cWPPnvRtyZj4NI8ztuimgIgSXxSmWMIGIqPpgEyN/UpWpKYJ59LVei0tOnLsdxMb5B7N1xrBWcQ6/7tmRggJQhRMVkU8W8xnRSpYpJOFlOSIPKBZJHEh/FbFGm9VcyOoYaqnyPqG9V6oUZUqkR9s14t+Pj7typhkmGU7hu6ltqPZQgA1dLDiFVPoTSJIp9J8gIvSOgfX4xcE/gQlUkSSQEQqZAU4oViloNJvgie3FPky+VYmahWc7mNSr2Qq7QQmPLUf713hcgYEwInTW9wOEEIXOZFGtYAA0JIwDPrBHVmXZoXbohUpohn1iEq6sw6DsEqGhmP2TFUCKJcr+Y3cq18pVLJ5ToE/jel7t5EH3t81Gfr70fnPtERVwzqq5lkKBol+FA2IgnZDJ5ZF8kKolAkRIIXGCGb5tMUejEoFo20+BNg6HTyxC5RqHaIVgzdrxL431SK3VV6FehS4WlKdBsVXDHoT6MeMIBMPsqnAccgT8GRAdRLcqhR0TCA3AgDMQDTgzyhp6j46QwMPdi7qdymPaLf0S/eTUByeVuLp8BdiCgypJhiTIDmSQ8Kdz6QUnsdldsTYdiYicLNPe2eFICjo50JRqBXkhbd3jc0ShVC51+qI4iREi5mTHFz74H5oMgFaL/iAlH3z4wxQKV6Rkm6lPrZwIWOKfYe3Bx5nEkXfSqd8bjaCmPwM5qwWtp8McRibz29N7eMKRwtCrq3LqOcL4bXHz7FNw9Nl29w1ZNi2MgVUNRQyE3VWb7ncgx5dn/KuvhKRaGA/wH2hWAotNZKulZak5zn6/ecx4qMxwWI3kK9Ku/aOyhdpMXwR9oBZSt1H/HEniJfRnXHWltRVSqV82Nev+M8FBNpF+9FWQYUFq9veQhAyAuD6iNIrbTRcCZm9XJWDButkkZgzSxLpZbXNbMP7rk8kwLG57Akla0hBGV+eGsFXRPqpqeY1DhsIKiZraGiG4IJQoVSqri+/m7MhULGHFQAzvxkNIp0tS+TJgFjfFbIcUaehHPJJE/tKWxeA85sDbXSipdKNefLH9686TxIELyRgge8gEJ9mob4N0ulOXSD7gcyNC8BDkCao0mYymZT2jAAMi7R9Lw9xcZayewTrKXKYc3+xd9zp0AkjS83GspIdDGSjhYjESDAIpPJiMlMRCSKUjKZLQaKkSLNSGKa13Nobq1C9xSz+IsZMGzYDWDNzmSEw97e6x5vlNIxMMlsMhsl6KxEkBl8wV2ET/J8MiuFmAgvRNFhOkaRUV6QzFbhhsERH02hmT2FVmvrz0gngUorhYcuflKVqIf4dCSbIUTiRkYiohGMISOJ1zJ8RhJofDEiur0hiHQxlczqXQiMjsEAmSmHJwDoWP1j2LVYgLN09A9XvN9JhJoBcxkuWrwmZDJRIZMFGTEtom6gmInw6Swv8dlINBPNUAw+yOg274EBQ6B7H7//ylR6/+X/0rLTNgyT14ioltaUyq45uwbzuOEv7j0Y81ai4cY5nEIORbmAEOWQp6CxUwA0h38gCKBDyiXrFk/hiYGC1PurfvQr4BI3tJSa6o82nf9X3ttHjPgLNbh2i55tGGxppWnzT14YIHjFFwXEgXFaQznXKed26/XqZr7cydWc8XFttGcc8RFW4WZxz6tvtGKYUa4YcBz0sk8Kq6vbzi6ynMvFKlVit1Kr14nNTcd/lSt51NzRLPJu0fNYDO5Q7IOB8dYAt31TWP14m3JgqOc3EIYyUc/ViWrV0VV4GYOti1hb+fCXDyb2M4anMEqVhpo3dMmhWYB5YfiVvZL9vlmO3tP1/rajb0AUYvl8faOa28gTuby9UWwYPUPJUfc19aD6xIfv/vceMUmKp/A7ZRoJelvD9sf2SnZPcXnY1R+b93S94sQwQZslzeh3CyU0kCp1SlV0W17rKHhqhXJpRRlt/PqNNzwGFzYMpPicf6U8rQFuO7qG7uH+fqy/v49+0N3Y2b7gaBXX/WLY1W2hkquVNiu7G7vlTqnT2t0o13Zbpcqb+TcrSu/x0RsfrriMLZwYmORzKb+SngNeGChXDP0u0uH+4enh2dFp12EN/jHobaKUb9Vb1d3d3Ju5aq1Q2c2V6pu7K29Wyp1Ozmg202G4BvCZd2UunPar3jBe1+QyKd8YDrvd07P9o66C4dTROVx3dJGm3Dq4nD68LtfL+VahU8uv5UsbtcpufhdZQalSaNWq+V3NX5TG5WAsGBgoihBfe9ljSKbH4lV+2B4AuldweAroD0O/f4S7xe7qURffontODNveGN66+8DRyRV0a9hdK9VWaq1SrVYr1Uq7K7VaFXUPtXK5hI5rI41SfUoMbLMZ7A0SxwkR9OIHPdBjG42Twc+BmVAzIyfoG8MUGoPh7pUrOzsf2EBU7f7B0G5Vc5xrxpOT+0gNA2ieiCfH8eP2yUBuHrTFE5aNn4TbXtND54ph5wrWzmgc2CmtrXiMJmyA0GtKE8/rqhjYRrN5Ig8T8WbidrDdDN4fso3wQbhJORKHGpX5Y7iyc8WaMSlPGFCMkClNPMuvYYgHg/FGAzQSrMwmZOogyPSaCTZBke6jifEY4lv+NRkDAvGBebBjYhgDRB9tT2kNeC4SngEIlEsR2WECPWbVuVrQxRietjXEHt578OD1B/fuPXy4t0dcMbVj5E2qRkZ+raKET2UUQOHwSTOT3XJprazDmBrDaKDMuM4Knd1T+MSwt4N1ZUfVFat29BOPFS3XgL5pFD5Vqzh8KpdaKHxq1XZrK6UciiAqJd1TTJz7oGCQOJ+hNI0xeGSfnhzDA2vVRzns7GivMcaXpXyt0KrW1PCpjiq/Uq/WSoVapYSjbIXVWmni/Dh85UDqJ/6vQMQZyadmDW8punv37gd3X7930wrByCBt6I2ilevkW5VyLb+SX8HhU24Fh0/VSh6NK/TXlKYaYcIxVxp6ifEcWj0tT2HzmXq0UEPh0xoaTrRaNdQ/1NZarQ4eY62gcbgxFN+dRMGSb5gm4zRazgdDTHeYd0ciqI7TQaih0m5Fe/ibN3RXMnk6mCMJ57XIkUufOR8MezsuEJTOwSMTq/P59Ue/0TBMHFKoGPy3CQDmisEBAckZQdoPfPRb9c7kNqFgAM/NcJU2/fQ8hU3IS7qdccNJlZHa62cnTA4fvqcYwxRTBRUMM16y7wvDERplzobhoftpR0KprONEhWVEhTj89jfowGQKGga8DIESN+EzJ0A99czgoNKrcwBTYugfdo/QqLp7dLTfP+p30Yj7rL/vxmPcQNtDhXHDCo3DRx+98ebEUbYFA9tgGRb0egOARhIUTsMMG2h0wXp4CmUdi8kY+sTRavfs9BChOD3q7q/un+GMi+BMPs2CwZqbtlZ9RB/9dnIGzsTAiPeHVHNwPxHvDRPtk6E4ZNvxeLuRAKNew681rB52949OD/vdVQ3D2eHZRVkDEXP3FDYcOz4wsCeNg5Nwoj2Q2+12ItE8FmH49pA6YCwpeqsnnRrD6urZ2dnq4Rkyin7/sI9ahSPxNDMG99N3tuRDXpkiPwUGVCcaHIgHJ8PjZkJuyu1EI37CsgfxBrIQ/WSFNu1XLzGGeXmKMaq/ueJ9NlsZcdTxrIbJUyDxeQqEgeoBkYrD3kDsUT1mGI8D2EuARHz0pJY5xvRhDU8TA2EMG2ylnmhQuse9hxPP12iNQrnGHui5aJBgNU/hdYbz24JBz1C7Nw0jfNyZDoNtTQ/ImOkWd9HTeYqnj4HY2C25AFDO39XMgeVbE+xBxUCJPkVhcn4wOE9bXhAGHE6WrJN+dEsYCR5jN8f3DxgDc+0//Gtqh7mKooSzfvd09ewI/fT7Z6v9I+QuzkZP2TwBBpyRszeN0optVLl3c6w9YE+B9yDwLdSFTBM+na3uH3XPjlDcdHZ42j3sdvf76OboEAWUwtlFYUBdZU2ZLK2aQanUckaO468bSDFjeoAJcp8JNxpMn6KgSQmZut3uGf5BMVT3aPX0tL9vpfCkGJBylQ5OQ7Y6FY9x9c6YHFRy9tku7vMiHX3D0WkfMVg97aPiEA0xDnEE5TiZ++QYJuued//Ag4lZJveZvjiV63y78Z6if3ioo7nALnJq7e15xpOZgFm5sUtsO63GY870nB2mH+3d9XwqZVslkbJcE+ZYJ9JaMh4z6L/FGMZMCxQomnScqbS0A+e8d/UIoD2up/hWYyAeePYPPBcIcL6EL7CRXK8zcsWgDKyfXvjkS+PGWSGfl1plMm6WoLyTHQNyCUf7qyhewsWqc5bLvDEQe+PmDF+U7OFTDIVPZ/t9FDfs91HktLp/uGgMk6YNX4js1nB0qqbe9o9Ojw5Pj/Zd0m9zxzBVHubJ5JZ9QoEz+jlFt2Ny0/PE4NU/CELIlwSvyzC//Z5C0Z7LtXchiXbb63GsooGk+wJuzwYGlzxMJOpY5IkcH1wrJeN+yf6zgsGeh8EbQVrHDlOczNYSs64bQT4zGGx5mBQ0RhC0Glbj+4w6gUENF6E1RWd54LYR5DODYTQPI5jGwGV4AAEN0S/N83wScIBEv1Q6GqHVw8q80IyxBZTb+o7PDoaRPIy64BG2ACiGhGiSj6RE9FssSmIqwnN8ROIJkQ/wETGFDjMknTWvu3XbCFLB4LiQYBoMY+ZMPy2ZeZgIp5u4uhFkNiVIgqhuBJnKUOkUkQpFCQkd5rNSNkBnxFB03GZvyoUEv/NP4X3fM+gvQg/1/sHEwMXwRpAR60aQkhji1eWq9I0gKSFLSPoV2x4YqO2X/GP4+Poitv0w8jDGZm8wmVE3gixKoWya59NSMZulQukQheyAy2aLUlFELSgQNfcY9loMjbruv3P4ZJtaxJr2eh5GW3wd2TnDQbwRZDTAp6PaRpAByOFfgDeCBAyAiuWYnsITw/Ynfi9A/N115yVn85E6zlJ2OTPjAlFEtRBJ5zIWbolbLwyQesknB4XCgtaLVPIw1h0Qp1kaz5qi9FwhEPUO3//dy69MheKVV97/+JPrL8GFYVD6h2k3ZoB62yHNKzFdVxaO4pciDtevf39affLStoJ3QTsx48UMbBh8TRF1/fZ0y9refmlabaPuEWNY2HLb71l3K/EnD2sg9EUu8D4DcPJWBChyQ69S/yQw+Rr9p6QPNvFiqPEZ5LWFjxAwLj2ZrrkZrw4sbnfyvXqCZcOffde3Pgt6RX3ZAPDC4Dhi6Zth1G3dxXmpXoPvDl582++Cum+/GPSM+gSe8Z3GCQRSLkuRzk+R4J07v/80TMKgMncaL6+rz/RhScA6u0ZS8RThFz2tAUsIZX0p5JXvn5fS7965896nYQh+FmbZoDzogWA8IbKAIYO3g/Ix6+oj4CQMz5wivd//4s6nYbYhxxvNxn25PThunBw35AErN4PDpm1RdkNLhyHABsUXw8Hb7YPm2712fNg8bstis82Kt+8Pgk2vbUERhqXb0Cn8YrjXCLcbzXi70Wv2GsNG/JiFwQYLjlnLgMJaLp01qBggIPFeVXgjSIYFwRM8Rxhfimn6M/1ctro+bHiMp3gWpWEgR79vZQ8fc51DozTWdVlOa7jQuOFZlILhsx/4lncU+UxK3extBjFL5yksI0xGLxn9/uhhywhz6axhmvyCsQKsZZXYZcMw47pPS4YBijNchplcOk8Bk9fANA3DelIbL1ywZBiUBY8c6z6R6Baom1W6lEuKgen1sHNghgCCAao+QgHQKJOE+gJ5FsFZrCE2s55a3S3SMbDNZjgRl5uJARjE7yfYIcMeHzcHB5aRtpGdp2bAEIttzKb5gMCncvFiaMzB7UE7npDbJ8N4u9kYNIOJxHFYbti3ndcNYhKG9C3x89feeecPP1a1sf/q87NqLhhUa2CPZfmgIQ/l5vB+EBnG/QEbb99uxM1VwGz5p8kYMIc//PgLpB9/EdtfnR0Dsoi5YECegh6y7DAeZ+UBmwCDhHgSJAE7iB/Hgc0MpreGWynxf0wKGMPVGYQw5OeEQekiSXzBFQQMCUiGHQ7wHAYGsCPb/9oXPJqA4db/fvFHlQJeHfJVk8L6unZrlOvo2OhRC4h5YlAqaHztDGOd8uY0hqkwJP+IhDgoFFZfNSnI9XVFW0opP1q/eo6OFc7Vo9qNiSGXnxuGmdZ98sIQI2I/Td9K/ulPf0IY/qhSsGIobF3d2jqXt/Jy/bxwLj+q1xGG80db8tb5+ZZ8Lte30M363DHMGEx7W8P9x4/PxD//WeGgUTAxrD+fr59v/WWr/pet80f1vxTOtx49Qhi25IJ8Xkc36InnF4IBrzZ+kUOrvS8fP27/9W9/xiDyxKodw9aj9dwWMonz/PnzW+f1cxndRRjO63U5t4VMAd1DN3PGwJETLqxyXRpPkReGn/7sq6/+769//RsC8dprQsyG4eqj9fVHqD9ABWLy6OrzV9Gd9av4ELojK8euynPuGzI+ttWwL7ftthEkQfzsq70vv3n8968xh9eQiJgNg+4N1td1P6EXWte4bjqTeWHQNoK0fvmkzUdoZuCYM01yrmdfY1/d//Kbb/7+NeLw+ecmhxEMfjQXDAQJXZZWt+414mwS+rNuG0Equo0w/OPrr0UVg8phVgwofJoHBq+NIK1y7xxozwkJP338+Jf/+setWxqG1wjkLV5dn1FzCZ/wRpAj3793ssVcUFWl4LoRpKqvvvnnv27hUYXGIZZf3SpszqRKfT4YiDQT4GjbP85Sjh5RRHOBwNhR9pf/JFUM76gS9k/zuZmUnxMFpGwk7VORrL//Aacb8rNpYz6JlzkpFsvnUZhdV/ModXS3auaX8gUlO4UOFkbSVMTc0k/z02a1QlTK9Uo1V60UCpuFTYIobOYqsfpmNd/q5Av5XLmaq+WqVYKoVAuVar1a6VQnr/T4rCmP93Uu4K2d0U8OVZIgWoXKZiHfqRTq+Xpho75JVCoEPl7FP9VNZDAzbYf8rVZ+c7NereeqhUIVWUa9U8nnN1H9UX0ruXo+16nmEIZqrtJBvNBrEKGlxJArFFBj0AqjLFf1+5r016gHp1nkcBk00/bXl7rUpS51qUtd6lKXutSllk3/D2YALCqhXlpOAAAAAElFTkSuQmCC)