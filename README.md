#20230412 homework question2
#定义三个字符数组: city[3][30], prov[3][30], addr[3][30]
# • city和prov的值分别是：（可不用cin输入）
#  – 你老家所在城市和省份
#  – 中山大学所在城市和省份
#  – 你某个好朋友读书所在城市和省份（如果上面有相同的信息，则另外选一个城市和省份
# • 通过字符串处理，得到addr的信息并输出（所在的城市和省份）。
#  – 如：city是Guangzhou，prov是Guangdong
#  – 经过字符串处理后，addr的值为：
#  – Guangzhou Guangdong
# • 找出按字母顺序排在最前的addr信息。
#include <iostream>#include <string>
#pragma warning(disable:4996)
using namespace std;
int main()
{
	char city1[3][50]; char prov[3][50];char addr[3][50]; int i;
	char city[3][50]; char string[3][10] = { {' '},{' '},{' '}};
	cout << "请依次输入您老家、中大、您朋友读书所在的城市：" << endl;
	for (i = 0; i < 3; i++)
	{	cin >> city1[i];
		strcpy(city[i], strcat(city1[i], string[i]));	
	}
	cout << "请依次输入您老家、中大、您朋友读书所在的省份：" << endl;
	for (i = 0; i < 3; i++)
	{	cin >> prov[i];
	}
	cout << "上述三个地址分别是：" << endl;
	for (i = 0; i < 3; i++)
	{	strcpy(addr[i], strcat(city[i], prov[i]));cout<< addr[i] << endl;
	}
	void front(char str[][50], int j);front(addr, 3);return 0;
}
void front(char str[][50], int n)
{	int i; char string[50];strcpy(string, str[0]);
	for (i = 0; i < n; i++)
	{	if (strcmp(str[i], string) < 0) strcpy(string, str[i]);
	}cout << "按字母顺序排在最前的地址：" << string << endl;
}
