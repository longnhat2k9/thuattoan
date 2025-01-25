# THUẬT TOÁN CẦN NHỚ

## 1. Tìm tổng các số từ 1 đến N
``` cpp
int s(const int &n)
{
	return (n*(n+1))/2;
}
```

## 2. Tìm tổng các số từ X đến (N nhân X)
```cpp
int s(const int &n)
{
	return ((n*(n+1))/2)*x;
}
```

## 3. Tìm tổng của bình phương các số từ 1 đến N
```cpp
int s (const int &n)
{
	return ((n*(n+1)*(2*n+1))/6);
}
```

## 4. Tìm ước chung lớn nhất của 2 số N và M (ĐK: N > M)
```cpp
int ucln(const int &n, const int &m)
{
	for(int i = m; i > 1; i--)
	{
		if((m%i == 0) && (n%i == 0))
			return i;
	}
	return 1;
}
```

## 5. Tìm bội chung nhỏ nhất của 2 số N và M (ĐK: N > M)
```cpp
int bcnn(const int &n, const int &m)
{
	for(int i = n; i < m*n; i++)
	{
		if((i%m == 0) && (i%n == 0))
			return i;
	}
	return m*n;
}
```

## 6. Tìm tổng số ước và tổng các ước của N
```cpp
void uoc(const int &n)
{
	long long sum = 0; int cnt = 0;
	for(int i = 1; i <= n; i++)
	{
		if(n%i == 0)
		{
			sum += i; //Tổng các ước
			cnt ++; //Tổng số ước
		}
	}
	cout << sum << endl;
	cout << cnt << endl;
}
```

## 7. Tìm số chữ số của N
```cpp
void sochuso(int &n)
{
	int s = 0;
	while (n > 0)
	{
		s++;
		n /= 10;
	}
	cout << s;
}
```

## 8. Tìm số lớn nhất trong ba số a, b, c
```cpp
void maxnum()
{
	int a, b, c; cin >> a >> b >> c;
	if(a < b)
		a = b;
	if(a < c)
		a = c;
	cout << a;
}
```

## 9. Tìm nghiệm của phương trình bậc 2 một ẩn ax^2 + bx + c = 0
```cpp
int giaiptbac2()
{
	int a, b, c; cin >> a >> b >> c;
	if(a == 0)
	{
		cout << "Khong phai phuong trinh bac hai mot an";
		exit(0);
	}
	int delta = b*b - 4*a*c;
	if(delta < 0)
	{
		cout << "Vo nghiem";
		exit(0);
	}
	else if(delta == 0)
	{
		cout << -b/2*a;
	}
	else
	{
		cout << (-b-sqrt(delta))/(2*a) << endl;
		cout << (-b+sqrt(delta))/(2*a) << endl;
	}
}
```

## 10. Giải phương trình bậc nhất 1 ẩn ax + b = 0
```cpp
int giaiptbacnhat1an()
{
	int a, b; cin >> a >> b; 
	if(a == 0)
	{
		cout << "Khong giai duoc";
		exit(0);
	}
	cout << -b/a;
}
```

## 11. Kiểm tra số N có phải số nguyên tố hay không
```cpp
bool checknto(const int &n)
{
	if((n%2 == 0) && (n > 2))
		return false;
	for(int i = 2; i <= sqrt(n); i++)
	{
		if(n%i == 0)
			return false;
	}
	return true;
}
```

## 12. Đảo ngược số N
```cpp
int daoso(int &n)
{
	int x = 0;
	while(n > 0)
	{
		x = x*10 + n%10;
		n =  n / 10;
	}
	return x;
}
```

## 13. Kiểm tra một số có thuộc dãy hạnh phúc hay không khi số đó không phải số nguyên tố (kiểm tra nó có phải ước của 1 trong các số đứng trước trong dãy)
### Dãy hạnh phúc là dãy từ N đến 1, các số trong dãy là số nguyên tố hoặc là ước của 1 trong các số đứng trước nó trong dãy
#### Chỉ kiểm tra nó có là ước của N hay không là đủ
```cpp
int checkuoc(const int &n, const int &x)
{
	if(n%x == 0)
	{
		return x;
	}
	return 0;
}
```

## 14. Tính số ước nhanh
```cpp
int souoc(int x)
{
	int cnt = 2;
	for(int i = 2; i <= sqrt(x); i++)
	{
		if(x%i == 0)
		{
			if(i == sqrt(x))
				cnt++;
			else
				cnt += 2;
		}
	}
	return cnt;
}
```

## 15. Xác định số nguyên tố hay không nhanh
```cpp
int ngto(int n)
{
	if(n==1)
		return 0;
	for(int i = 2; i <= sqrt(n); i++)
	{
	  if(n%i == 0) 
	  	return 0;
	}	
	return 1;
}
```

## 16. Tìm tổng ước nhanh
```cpp
long long tonguoc(const int &n)
{
	long long tonguoc = n + 1; 
	for(int i = 2; i <= sqrt(n); i++)
	{
		if(n%i == 0)
		{
			if(i == sqrt(n))
				tonguoc = tonguoc + i;
			else
				tonguoc = tonguoc + i + n/i;
		}
	}
	return tonguoc;
}
```

## 17. Tìm ucln nhanh
```cpp
int ucln(int n, int m)
{
	int r;
	while(m%n != 0)
	{
		r = m%n;
		m = n;
		n = r;
	}
	return n;
}
```

## 18. Tìm bcnn nhanh
```cpp
int bcnn(int n, int m)
{
	return m*n/ucln(n, m);
}
```

## 19. Sắp xếp các số chẵn tăng dần lên trước và các số lẻ giảm dần ra sau
```cpp
void cs()
{
	int n; cin >> n; int a[n]; for(int i = 0; i < n; i++) cin >> a[i];
	int c = 0, l = n - 1;
	while(l > c)
	{
		while(a[c]%2 == 0 && c <= n) c++;
		while(a[l]%2 != 0 && l >= 0) l--;
		if(c < l) 
		{
			swap(a[l], a[c]);
			c++; l--;
		}
	}
	sort(a, a + c); sort(a + c, a + n, greater<int>());
	for(int i : a) cout << i << " ";
}
```

## 20. Sắp xếp giá trị tuyệt đối tăng dần
```cpp
bool cmp(int x, int y)
{
	if(abs(x) == abs(y) and (x > y)) return true;
	return abs(x) < abs(y);
}

int main()
{
	int n; cin >> n; int a[n]; for(int i = 0; i < n; i++) cin >> a[i];
	sort(a, a + n, cmp);
	for(int i : a) cout << i << " ";
}
```

## 21. Tính tổng các chữ số của N
```cpp
int tongtach(int n)
{
    int a, tong = 0;
    while(n != 0)
    {
        a = n%10;
        tong = tong + a*a;
        n = n/10;
    }
    return tong;
}
```

## 22. Đếm số lượng số 0 tận cùng của N
```cpp
int dem0(int n)
{
	int count = 0;
	for(int i = 5; n / i >= 1; i *= 5)
		count += n/i;
	return count;
}
```

## 23. Lũy thừa nhị phân a mũ b
```cpp
const long long mod = 1e9 + 7;
long long pow(long long a, long long b)
{
	long long s = 1;
	if(b == 0)
		return s;
	while(b)
	{
		if(b%2 == 1)
		{
			s = (s%mod * a%mod) %mod;
		}
		a = (a%mod * a%mod) %mod;
		b = b / 2;
	}
	return s;
}
```

## 23. Lũy thừa nhị phân a mũ b mũ c
```cpp
const long long mmod = 1e9 + 7;

long long pow(long long a, long long b, long long mod)
{
	long long s = 1;
	if(b == 0)
		return s;
	while(b)
	{
		if(b%2 == 1)
		{
			s = (s%mod * a%mod) %mod;
		}
		a = (a%mod * a%mod) %mod;
		b = b / 2;
	}
	return s;
}

int main()
{
    int a, b, c; cin >> a >> b >> c;
    cout << pow(a%mmod, pow(b%mmod, c, mmod - 1), mmod) << endl;
}
```

## 24. Kiểm tra N có là số chính phương hay không
```cpp
bool uocphu (const int &n)
{
	for(int i = 2; i <= sqrt(n); i++)
	{
		if(n%i == 0)
		{
			if(i != sqrt(n))
				return true;
		}
	}
	return false;
}

int main()
{
    int n; cin >> n;
    if(sqrt(n) == int(sqrt(n)) and uocphu(n) == false) cout << "True";
}
```

## 25. Đếm số ước nguyên tố của N
```cpp
int demnto(int n)
{
    int dem = 0;
    for(int i = 2; i <= sqrt(n); i++)
    {
        if(n%i == 0)
        {
            dem++;
        }
    }
    return dem
}
```

## 26. Phân tích N thành thừa số nguyên tố
```cpp
int findnt(int n, int nto)
{
	bool check = true;
	for(int i = nto + 1; i <= n; i++)
	{
		for(int j = 2; j <= sqrt(i); j++)
		{
			if(i%j == 0)
				check = false;
		}
		if(check == false)
			check = true;
		else
			return i;
	}
}

int main()
{
	int n; cin >> n; int nto = 2; int mu = 0;
	while(n != 1)
	{
		mu = 0;
		
		while(n%nto == 0)
		{
			mu++;
			n = n/nto;
		}
		if(mu != 0)
		{
			cout << nto << "^" << mu;
			if(n != 1)
				cout << " * ";
		}
		nto = findnt(n, nto);
	}
}
```

## 27. Tổng các giai thừa từ 1 đến N
```cpp
int cs()
{
    int n; cin >> n; long long gt = 1; long long tong = 1;
    for (int i = 2; i <= n; i++)
    {
        gt = gt*i;
        tong = tong + gt;
    }
    return tong
}
```

## 28. Kiểm tra N có là số hoàn hảo hay không (Phi hàm Euler)
```cpp
bool nto(long long n)
{
    for(long long i = 2; i < sqrt(n); i++)
    {
        if(n%i == 0) return false;
    }
    return true;
}

bool hoanhao(long long n)
{
    for(long long i = 2; i <= 32; i++)
    {
        if(nto(i))
        {
            long long t = pow(2, i - 1), t2 = (t*2) - 1;
            if(nto(t2) && n == t*t2) return true;
        }
    }
    return false;
}
```

## 29. Tính số ước các số từ 1 đến N
```cpp
vector<int> demuoc()
{
    vector<int>a(n, 1);
    for(int i = 2; i <= n; i++)
    {
        for(int j = i; j < n; j += i)
        {
            a[j]++;
        }
    }
}
```

## 30. Tìm K sao cho tổng từ 1 tới K nhỏ hơn hoặc bằng N
```cpp
void cs()
{
    long long n; cin >> n; 
    long long k = sqrt(2*n);
    if(k*(k + 1) <= 2*n)
    {
        cout << k;
    }
    else
    {
        cout << k - 1;
    }
}
```

## 31. Tìm số nguyên dương L nhỏ nhất sao cho tất cả các dãy con gồm L phần tử liên tiếp của dãy A đều có tổng lớn hơn hoặc bằng M.
```cpp
int main()
{
    long long n, k; cin >> n >> k; vector<long long>a(n);
    for(int i = 0; i < n; i++) cin >> a[i];
    long long r = 0, l = 0, sum = 0, mx = -1;
    for(r = 0; r < n; r++)
    {
        sum += a[r];
        while(sum >= k)
        {
            mx = max(mx, r - l + 1);
            sum -= a[l];
            l++;
        }
    } 
    while(sum < k and mx != -1)
    {
        l--;
        sum += a[l];
        mx = max(mx, r - l);
    }
    cout << mx;
}
```

## 32. Sàng số nguyên tố các số từ 1 đến N
```cpp
vector<int>sang(int n)
{
    vector<int>a(n + 1, 1); a[0] = a[1] = 0;
    for(int i = 2; i <= sqrt(n); i++)
    {
        if(a[i] == 0)
        {
            for(int j = i * i; j <= n; j += i) a[j] = 0;
        }
    }
    return a;
}
```

## 33. Sàng số nguyên tố trên đoạn từ L đến N

```cpp
vector<int> sang(long long n, long long l)
{
    vector<int>a(n - l + 1, 1);
    for(long long i = 2; i <= sqrt(n); i++)
    {
        for(long long j = max((i * i), ((l + i - 1)/(i * i))); j <= n; j += i) a[j - l] = 0;
    }
    return a;
}
```

## 34. Đếm phân phối
```cpp
const int m = 1e6;

vector<int> dpp()
{
	vector<int>a(m, 0);
	for(int i = 0; i < n; i++)
	{
		int x; cin >> x;
		a[x]++;
	}
	return a;
}
```

## 35. Mảng cộng dồn (Prefix Sum)
```cpp
vector<int> prf()
{
	int n; cin >> n;
	vector<int>a(n); cin >> a[0];
	for(int i = 1; i < n; i++)
	{
		cin >> a[i];
		a[i] = a[i] + a[i - 1];
	}
	return a;
}