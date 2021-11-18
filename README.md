alternatif = ["Kota A,Kota B,Kota C,Kota D,Kota E"]
kriteria = ["Kisaran harga,Customer Service,Support System,Pilihan pembayaran, Jumlah Server"]
costbenefit = ["cost,benefit,benefit,benefit,benefit"]
kepentingan = [0.18,0.3,0.18,0.11,0.23]

alternatifkriteria = [
    [5,4,10.0,4,120],
    [4,4,5.0,4,87],
    [5,5,7.5,3,67],
    [4,4,4.0,5,98],
    [3,3,25.0,4,100]
]

print(str(alternatif))
print(str(kriteria))
print(str(costbenefit))
print(str(kepentingan))
print(str(alternatifkriteria))

pembagi=[]
for i in range (len(kriteria)):
    pembagi.append(0)
    for j in range (len(alternatif)):
         if costbenefit[i] == 'cost':
            if j == 0:
                pembagi [i] = alternatifkriteria[j][i]
            else :
                if pembagi [i] < alternatifkriteria[j][i]:
                    pembagi [i] = alternatifkriteria [j][i]
    else : #if costbenefit[i] == 'benefit':
        if j == 0:
            pembagi [i] = alternatifkriteria [j][i]
        else :
            if pembagi [i] < alternatifkriteria [j][i]:
                pembagi [i] = alternatifkriteria [j][i]i]:
            pembagi [i] = alternatifkriteria [j][i]
			
print(str(pembagi))

normalisai = []

for i in range (len(alternatif)):
    normalisai.append([])
    for j in range (len(kriteria)):
        normalisai[i].append(0)
        if costbenefit[j] == 'cost':
            normalisai [i][j] = pembagi [j] / alternatifkriteria[i][j]
            else : #if costbenefit[j] == 'benefit':
                normalisai [i][j] = alternatifkriteria [i] /pembagi[j]
				
print(str(normalisai))

hasil = []

for i in range (len(alternatif)):
    hasil.append(0)
    for j in range (len(kriteria)):
        hasil[i] = hasil[i]+ (normalisai[i][j]*kepentingan[j])
		
print(str(hasil))

alternatifrangking=[]
hasilrangking=[]

for i in range(len(alternatif)):
    hasilrangking.append(hasil[i])
    alternatifrangking.append(alternatif[i])
	
for i in range(len(alternatif)):
    for j in range(len(alternatif)):
        if j > i :
            if hasilrangking[j]> hasilrangking [i]:
            tmphasil = hasilrangking [i]
			tmpalternatif = alternatifrangking [i]
			hasilrangking[i] = alternatifrangking [j] 
			hasilrangking [j] = tmphasil
			alternatifrangking[j] = tmpalternatif
			
print(str(alternatifrangking))	
print(str(hasilrangking))		
