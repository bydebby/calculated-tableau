# DATE
* Date
  
  Example: 20190228
  ```
  LEFT([Periode],4)  = 2019
  MID([Periode],5,2) = 02
  RIGHT([Periode],2) = 28

  DATE(LEFT([Periode],4)+'-'+MID([Periode],5,2)+'-'+RIGHT([Periode],2))
  ```
* Datetime

  `DATETIME([Periode])`

* STR Date

  Example: 20190228
  ```
  DAY([Tanggal]) = 28
  DATENAME('month',[Tanggal]),3 = Feb

  STR(DAY([Tanggal]))+' '+LEFT(DATENAME('month',[Tanggal]),3)
  ```
* STR Tahun
  
  `STR(YEAR([Tanggal]))`

* Max Date
  
  `{MAX([Tanggal])}`

* Min Date
  
  `{MIN([Tanggal])}`

* Start date
  
  `DATEADD('day',-9,[Max_Tanggal])`

* Filter Date

  `[Tanggal]>=[StartDate]`

# SYNONIM
  ```
  IF CONTAINS([Bahan Aktiif1],'AZITHROMYCIN')
  THEN 'AZITHROMYCIN'
  ELSEIF CONTAINS([Bahan Aktiif1],'DEXAMETHASONE')
  THEN 'DEXAMETHASONE'
  ELSEIF  CONTAINS([Bahan Aktiif1],'FAVIPIRAVIR') 
  THEN 'FAVIPIRAVIR' 
  ELSEIF CONTAINS([Bahan Aktiif1],'REMDESIVIR')
  THEN 'REMDESIVIR'
  ELSEIF CONTAINS([Bahan Aktiif1],'HUMAN NORMAL IMMUNOGLOBULIN') 
  THEN 'HUMAN NORMAL IMMUNOGLOBULIN'
  ELSEIF CONTAINS([Bahan Aktiif1],'OSELTAMIVIR')
  THEN 'OSELTAMIVIR PHOSPHATE'
  ELSEIF CONTAINS([Bahan Aktiif1],'TOCILIZUMAB')
  THEN 'TOCILIZUMAB'
  ELSEIF CONTAINS ([Bahan Aktiif1],'IVERMECTIN')
  THEN 'IVERMECTIN'
  ELSE ''
  END
  ```
# Filter
  ```
  IF [kelompokbahanaktif]='DEXAMETHASONE' 
  AND [Sediaan] = 'CAIRAN INJEKSI'
  THEN 'CAIRAN INJEKSI'
  ELSEIF [kelompokbahanaktif]!='DEXAMETHASONE' 
  AND [Sediaan] != 'CAIRAN INJEKSI'
  THEN [Sediaan]
  END
  ```
  ```
  IF [kel_bahan_aktif]='DEXAMETHASONE' 
  AND [Sediaan] = 'CAIRAN INJEKSI'
  THEN 'CAIRAN INJEKSI'
  ELSEIF [kel_bahan_aktif]!='DEXAMETHASONE' 
  THEN [Sediaan]
  END
  ```
  
# IF ELSE 
  ```
  Example: 
  If stock a is not exist then stock b
  if stock a is exist then stock a + stock c
  ```
  ```
  IF ISNULL(INT([stock a])) then int([stock b])
  ELSE INT([stock a]) + INT([stock c])
  END
  ```
