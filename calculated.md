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
* Filter Dexamethasone is Cairan Injeksi
  
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
* Filter last 5 months
  
  ```
  DATEDIFF('month',[created_at],TODAY()) = 0 or
  DATEDIFF('month',[created_at],TODAY()) = 1 or
  DATEDIFF('month',[created_at],TODAY()) = 2 or
  DATEDIFF('month',[created_at],TODAY()) = 3 or
  DATEDIFF('month',[created_at],TODAY()) = 4
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

# COUNT INCLUDED VALUE 0
* Calcultae IF ELSE Included Value 0 -> [Jumlah]

  >IF COUNT([id]) > 0 THEN COUNT([id]) ELSE 0 END

* Calculated WINDOW SUM

  >WINDOW_SUM([Jumlah], 0, 0)

# CASE WHEN MONTH
  
  `Example bulan_tahun = 202201`
  ```
  CASE RIGHT([bulan_tahun],2)
  WHEN '01' THEN 'Januari'
  WHEN '02' THEN 'Februari'
  WHEN '03' THEN 'Maret'
  WHEN '04' THEN 'April'
  WHEN '05' THEN 'Mei'
  WHEN '06' THEN 'Juni'
  WHEN '07' THEN 'Juli'
  WHEN '08' THEN 'Agustus'
  WHEN '09' THEN 'September'
  WHEN '10' THEN 'Oktober'
  WHEN '11' THEN 'November'
  WHEN '12' THEN 'Desember'
  END
  ```
