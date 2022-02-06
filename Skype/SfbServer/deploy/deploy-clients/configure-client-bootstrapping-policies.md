---
title: 클라이언트 부트스트래핑 정책 구성
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: '요약: 그룹 정책을 관리하는 방법'
---

# <a name="configure-client-bootstrapping-policies"></a>클라이언트 부트스트래핑 정책 구성
 
**요약:** 그룹 정책을 관리하는 방법
  
GPMC(그룹 정책 관리 콘솔) 및 그룹 정책 개체 편집기는 그룹 정책을 관리하는 데 사용하는 도구입니다. Office 그룹 정책 관리 템플릿에 포함된 lync16.admx(ADMX) 및 ADML(.adml) 관리 템플릿에는 도메인의 그룹 정책 개체에 대해 구성하는 비즈니스용 Skype 대한 레지스트리 기반 정책 설정이 포함되어 있습니다. ADML 파일은 ADMX 파일에 대한 언어별 보완입니다. 각 ADMX 및 ADML 파일에는 단일 응용 프로그램에 대한 정책 Office 포함되어 있습니다. Microsoft 다운로드 센터에서 Office [2016 관리 템플릿 파일(ADMX/ADML](https://www.microsoft.com/download/details.aspx?id=49030))을 무료로 다운로드할 수 있습니다.
  
비즈니스용 Skype 클라이언트의 경우 사용자가 처음으로 서버에 로그인하기 전에 구성을 고려해야 하는 몇 가지 클라이언트 부트스트래프 정책이 있습니다. 예를 들어 로그인이 완료될 때까지 클라이언트가 사용해야 하는 기본 서버 및 보안 모드입니다. 그룹 정책을 사용하여 사용자가 로그인하고 서버에서 인밴드 프로비전 설정을 수신하기 전에 사용자의 컴퓨터 레지스트리에서 이러한 설정을 설정할 수 있습니다. 다음 표에는 그룹 정책 설정에 사용할 수 있는 그룹 정책 설정이 비즈니스용 Skype.
  
**그룹 정책 설정 정책 비즈니스용 Skype**

|그룹 정책 설정|설명|
|:-----|:-----|
|서버 지정(ConfigurationMode)  <br/> | 로그인하는 비즈니스용 Skype 전송 및 서버를 식별하는 방법을 지정합니다. 이 설정 내에서 다음을 지정합니다. <br/>  ServerAddressExternal: 외부 방화벽 외부에서 연결할 때 클라이언트 및 페더임 연락처에서 사용하는 서버 이름 또는 IP 주소를 지정합니다. <br/>  ServerAddressInternal: 클라이언트가 조직의 방화벽 내부에서 연결할 때 사용되는 서버 이름 또는 IP 주소를 지정합니다. <br/>  전송: TCP(Transmission Control Protocol) 또는 TLS(전송 계층 보안)를 지정합니다. <br/> |
|지원되는 추가 서버 버전(ConfiguredServerCheckValues)  <br/> |기본적으로 지원되는 서버 버전 외에도 로그온할 서버 비즈니스용 Skype 서버 이름 목록을 세미 콜론으로 구분하여 지정합니다.  <br/> |
|로그인 실패 로그의 자동 업로드 사용 안 합니다(DisableAutomaticSendTracing)  <br/> |분석을 위해 로그인 실패 로그를 비즈니스용 Skype 서버 업로드합니다. 로그인에 성공하면 로그가 자동으로 업로드되지 않습니다. 해당 정책이 구성되지 않은 경우 다음과 같은 상황이 발생합니다.  <br/> 온라인 비즈니스용 Skype: 로그인 실패 로그가 자동으로 업로드됩니다. 비즈니스용 Skype 사용자: 업로드하기 전에 사용자에게 확인 대화 상자가 표시됩니다. 이 설정을 사용하지 않도록 설정하면 로그인 로그가 비즈니스용 Skype 서버 및 비즈니스용 Skype 온라인 사용자 모두에 대해 비즈니스용 Skype 업로드됩니다. 이 설정을 사용하도록 설정하면 로그인 로그가 자동으로 업로드되지 않습니다.  <br/> |
|SIP 연결에 HTTP 폴백 사용 안 끊기(DisableHttpConnect)  <br/> |TLS 비즈니스용 Skype 서버 TCP를 사용할 수 없는 경우 HTTP를 사용하여 서버에 연결하지 못하게 합니다. 기본적으로 비즈니스용 Skype TLS 또는 TCP를 사용하여 서버에 연결하려고 시도하며, 이러한 전송 방법이 모두 성공하지 못하면 비즈니스용 SKYPE HTTP를 사용하여 연결을 시도합니다. 이 정책을 사용하여 대체 HTTP 연결 시도를 사용하지 않도록 설정할 수 있습니다.  <br/> |
|로그온 자격 증명 필요(DisableNTCredentials)  <br/> |사용자가 SIP 서버에 로그인하는 동안 비즈니스용 Skype 자격 증명을 자동으로 사용하는 Windows 자격 증명을 제공해야 합니다.  <br/> |
|서버 버전 확인을 사용하지 않도록 설정(DisableServerCheck)  <br/> |해당 정책을 1로 설정하면 로그인하기 비즈니스용 Skype 서버 이름 및 버전을 확인할 수 없습니다. 기본적으로 비즈니스용 Skype 전에 이러한 검사를 합니다.  <br/> |
|BITS를 사용하여 주소 책 서비스 파일 다운로드 사용(EnableBitsForGalDownload)  <br/> |BITS(비즈니스용 Skype)를 사용하여 주소 Background Intelligent Transfer Service 파일을 다운로드할 수 있습니다.  <br/> |
|SIP 보안 모드 구성(EnableSIPHighSecurityMode)  <br/> |인스턴트 비즈니스용 Skype 보다 안전하게 보내고 받을 수 있습니다. 이 정책은 Windows .NET 또는 Microsoft Exchange Server 서비스에는 적용되지 않습니다.  <br/> 이 정책 설정을 구성하지 않는 경우 전송을 비즈니스용 Skype 수 있습니다. 그러나 TLS를 사용하지 않는 경우 서버에서 사용자를 인증하는 경우 비즈니스용 Skype NTLM 또는 Kerberos 인증을 사용해야 합니다.  <br/> |
|전체 주소장 다운로드 초기 지연(GalDownloadInitialDelay)  <br/> |GAL(전체 주소 목록)을 다운로드하기 전의 기간을 지정합니다. 기본값은 60분으로, 서버에서 0분에서 60분 사이의 임의 기간 동안 GAL 파일 다운로드를 지연합니다.  <br/> |
|사용자가 웹 응용 비즈니스용 Skype 방지(PreventRun)  <br/> |사용자가 웹 응용 비즈니스용 Skype. 컴퓨터 구성 및 사용자 구성 모두에서 이 정책 설정을 구성할 수 있지만 컴퓨터 구성의 정책 설정이 우선합니다.  <br/> |
|사용자 암호 저장 허용(SavePassword)  <br/> |암호를 비즈니스용 Skype 수 있습니다.  <br/> |
|SIP 압축 모드 구성(SipCompression)  <br/> |SIP 압축을 설정할 시점을 지정합니다. 기본적으로 SIP 압축은 어댑터 속도에 따라 설정됩니다. 이 정책을 설정하면 로그인 시간이 길어질 수 있습니다.  <br/> |
|신뢰할 수 있는 도메인 목록(TrustModelData)  <br/> |고객 SIP 도메인의 prefix와 일치하지 않는 신뢰할 수 있는 도메인을 나열합니다.  <br/> |
   
서버에 구성된 정책은 사용자가 구성한 그룹 정책 설정 또는 클라이언트 옵션보다 우선적으로 적용됩니다. 다음 표에는 설정이 충돌하는 경우의 적용되는 순서가 요약되어 있습니다.
  
**그룹 정책 우선 순위**

|**우선 순위**|**설정 위치 또는 방법**|
|:-----|:-----|
|1  <br/> |비즈니스용 Skype 서버 프로비전  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |옵션 대화 상자의 비즈니스용 Skype  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>관리 템플릿 파일을 사용하여 그룹 정책 비즈니스용 Skype 정의하려면

1. 루트 수준 폴더를 만들어 모든 언어 중립 ADMX 파일을 포함하세요. 예를 들어 다음과 같이 이 위치에 도메인 컨트롤러의 중앙 저장소에 대한 루트 폴더를 만듭니다.
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 이 절차에서는 도메인에서 여러 컴퓨터를 관리하려는 것으로 가정합니다. 이 경우 기본 도메인 컨트롤러의 Sysvol 폴더에 있는 중앙 저장소에 템플릿을 저장합니다. 이를 통해 도메인 관리 템플릿에 대한 복제된 중앙 저장 위치가 마련됩니다. 
  
2. 사용할 각 언어에 대한 하위폴더를 만들 수 있습니다. 이러한 하위 폴더에는 언어별 ADML 리소스 파일이 포함되어 있습니다. 예를 들어 이 위치에 미국 영어(EN-US)에 대한 하위폴더를 만들 수 있습니다.
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

