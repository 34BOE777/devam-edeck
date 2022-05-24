mainde nesneler için vector yapılması gerekiyor. farklı nesneleri vectorde tutabilmek için virtual fonksiyon gerek #include<iostream>
#include<iomanip>
using namespace std;
class arac{
private:
	string renk;
	int teker;
	string yakit;
	int hiz;
public: 
	arac(string renk,int teker,string yakit,int hiz):renk(renk),teker(teker),yakit(yakit),hiz(hiz){}
	
	string getrenk(){
		return renk;
	}
	string getyakit(){
		return yakit;
	}

	int getteker(){
		return teker;
	}
	int gethiz(){
		return hiz;
	}
	/*void basla(){
		cout<<"Araç harekete başladı. "<<endl;
	}

	void accel(){
		int i=0;
		while(i<=hiz){
			i++;
		}
		cout<<"Aracın hızı maksimumda! "<<endl;
	}
	*/
	void yazdir(){
		cout<<renk<<"  "<<teker<<"  "<<yakit<<"  "<<hiz<<endl;
	}
};

class yolcu:public arac{
private: 
	int koltuk;
public:
	int getkoltuk(){
		return koltuk;
	}
	yolcu(string renk,int teker,string yakit,int hiz,int koltuk):arac(renk,teker,yakit,hiz),koltuk(koltuk){}
};

class araba:public yolcu{
private:
	int kapisayisi;
public:
	araba(string renk,int teker,string yakit,int hiz,int koltuk,int kapisayisi):yolcu(renk,teker,yakit,hiz,koltuk),kapisayisi(kapisayisi){}
void yazdir(){
	cout<<getrenk()<<"  "<<getteker()<<"  "<<getyakit()<<"  "<<gethiz()<<getkoltuk()<<kapisayisi<<endl;
	
}
};
class motor:public yolcu{
private:
	int eyer;
public:
motor(string renk,int teker,string yakit,int hiz,int koltuk,int eyer):yolcu(renk,teker,yakit,hiz,koltuk),eyer(eyer){}
};

class nakliye:public arac{
private:
	int kapisayisi;
	int kapasite;
public:
	nakliye(string renk,int teker,string yakit,int hiz,int kapisayisi,int kapasite):arac(renk,teker,yakit,hiz),kapisayisi(kapisayisi),kapasite(kapasite){}
	int getkapisayisi(){
		return kapisayisi;
	}
	int getkapasite(){
		return kapasite;
	}
};
	class tir:public nakliye{
	private:
		int boyut;
	public:
		tir(string renk,int teker,string yakit,int hiz,int kapisayisi,int kapasite,int boyut):nakliye(renk,teker,yakit,hiz,kapisayisi,kapasite),boyut(boyut){}
		int getboyut(){
			return boyut;
		}
		
		  

	
};

