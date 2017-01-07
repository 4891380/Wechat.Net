# WeChat

#### 1����ʼ��������

```csharp
 WeChatSDK.Initialize(
                "�����˺�Ӧ��ID",
                "�����˺�Ӧ����Կ",
                "΢֧���̻���",
                "΢֧����key",
                @"΢֧��֤��·��",
                "΢��֧���첽֪ͨ�ص���ַ");
```

### 2��΢��֧��

```csharp
var p = new Pay();

// ��ɨ�븶 NativePay�� 
// �����������š�����ƷID����Ʒ����
var result = p.NativePay("201701071230300001", 1, "10001", "������ƷA");
if (result.return_code.Equals("SUCCESS") && result.result_code.Equals("SUCCESS"))
{
    // ������
    var prepay_id = result.prepay_id;
    // �������ӣ���������ӵ�ַʤ����ά�룬��΢��ɨ��֧��
    var code_url = result.code_url;
}


// ����ҳ�����ں�֧�� H5Pay��
// ���ޣ������š�������openid����Ʒ����
var result2=  p.H5Pay("201701071230300002", 1, "10001", "������ƷA");
if (result2.return_code.Equals("SUCCESS") && result2.result_code.Equals("SUCCESS"))
{
    // ������
    var prepay_id = result2.prepay_id;
}

// ��APP֧�� APPPay��
// ���ޣ��豸�š������š���������Ʒ����
var result3=  p.APPPay("1234567","201701071230300003", 1, "������ƷA");
if (result3.return_code.Equals("SUCCESS") && result3.result_code.Equals("SUCCESS"))
{
    // ������
    var prepay_id = result3.prepay_id;
}
```