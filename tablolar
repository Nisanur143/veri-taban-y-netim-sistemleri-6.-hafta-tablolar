# veri-taban-y-netim-sistemleri-6.-hafta-tablolar
aciklama.

--create database kutuphaneSistemi
use kutuphaneSistemi
create table adresler(
adresNo int Primary key not null identity(1,1),
sehir nvarchar(50), 
binaNo int,
postakodu int,
ulke nvarchar(50) not null,
cadde nvarchar(50)
);

create table uyeler(
uyeNo int Primary key identity(1,1),
uyeAdi nvarchar(100),
uyeSoyadi nvarchar(100),
cinsiyet char(20),
telefon nvarchar(50),
eposta nvarchar(50)
);

alter table Uyeler
add adresNo INT 
constraint "uyeler_adresler" 
foreign key(adresNo) References Adresler(adresNo);

create table kutuphane(
kutuphaneNo int Primary key,
kutuphaneIsmi nvarchar(50),
Aciklama nvarchar(50),
adresNo int foreign key(adresNo) References Adresler(adresNo)
);

create table kitaplar(
ISBN nvarchar(50) not null primary key,
kitapAdi nvarchar(50),
sayfaSayisi int,
YayinTarihi datetime
);

create table emanet(
emanetNo int primary key not null identity(1,1),
emanetTarihi datetime,
teslimTarihi datetime,
uyeNo int foreign key (uyeNo)references Uyeler(uyeNo),
ISBN nvarchar(50) foreign key (ISBN) references Kitaplar (ISBN)
);

create table kategori(
kategoriNo int primary key identity(1,1),
kategoriAdi nvarchar(100)
);

create table yazarlar(
yazarNo int primary key identity(1,1) not null,
yazarAdi nvarchar(50),
yazarSoyadi nvarchar(50)
);

create table kitap_yazarlar(
id int primary key not null identity(1,1),
ISBN nvarchar(50) foreign key (ISBN) references kitaplar (ISBN),
yazarNo int foreign key (yazarNo) references yazarlar (yazarNo)
);

create table kitap_kutuphane(
id int primary key identity(1,1),
miktar int,
ISBN nvarchar(50) foreign key (ISBN) references kitaplar (ISBN),
kutuphaneNo int foreign key (kutuphaneNo) references kutuphane (kutuphaneNo)
);

select * from Uyeler
select * from Adresler
select * from emanet
select * from kategori
select * from kitap_kutuphane
select * from kitap_yazarlar
select * from kitaplar
select * from kutuphane
select * from yazarlar

insert into Adresler values ('Kayseri',38,2700,'Türkiye','15 Temmuz')
insert into Adresler(sehir,ulke) values ('istanbul','türkiye')
insert into Uyeler values ('Nisanur','Yagimli','F',null,'nisanur@gmail.com',null)
insert into emanet(emanetTarihi,teslimTarihi) values(30-03-2026,30-04-2026)
insert into kategori values ('edebiyat')
insert into kitap_kutuphane values (2,null,null)
insert into kitap_yazarlar values (null,null)
insert into kitaplar values ('A123','Harry Potter',278,null) 
insert into kutuphane values (1,'Hogwarts Kutuphane',null,1)
insert into yazarlar values ('JK','Rowling')
