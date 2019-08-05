---
title: 클라이언트 부트스트랩 정책 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: '요약: 그룹 정책을 관리 하는 방법입니다.'
ms.openlocfilehash: 29e60ea772348ed5f483669cc1d17f8c13e96a02
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190476"
---
# <a name="configure-client-bootstrapping-policies"></a>클라이언트 부트스트랩 정책 구성
 
**요약:** 그룹 정책을 관리 하는 방법
  
GPMC (그룹 정책 관리 콘솔) 및 그룹 정책 개체 편집기는 그룹 정책을 관리 하는 데 사용 하는 도구입니다. Office 그룹 정책 관리 서식 파일에는 도메인의 그룹 정책 개체에 대해 구성 하는 비즈니스용 Skype에 대 한 레지스트리 기반 정책 설정이 포함 된 lync16 (ADMX) 및 adml (ADML) 관리 서식 파일이 포함 되어 있습니다. ADML 파일은 ADMX 파일에 대 한 언어 관련 보완입니다. 각 ADMX 및 ADML 파일에는 단일 Office 응용 프로그램에 대 한 정책 설정이 포함 되어 있습니다. Microsoft 다운로드 센터에서 [Office 2016 관리 템플릿 파일 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) 을 무료로 다운로드할 수 있습니다.
  
비즈니스용 Skype 클라이언트에는 사용자가 처음으로 서버에 로그인 하기 전에 구성 하는 데 고려해 야 하는 여러 가지 클라이언트 부트스트랩 정책이 있습니다. 예를 들어 클라이언트에서 로그인이 완료 될 때까지 사용 해야 하는 기본 서버 및 보안 모드입니다. 그룹 정책을 사용 하 여 로그인 하 고 서버에서 대역내 프로비저닝 설정 수신을 시작 하기 전에 사용자의 컴퓨터 레지스트리를 이러한 설정으로 설정할 수 있습니다. 다음 표에는 비즈니스용 Skype에서 사용할 수 있는 그룹 정책 설정이 나와 있습니다.
  
**비즈니스용 Skype에 대 한 그룹 정책 설정**

|그룹 정책 설정|설명|
|:-----|:-----|
|서버 지정 (ConfigurationMode)  <br/> | 비즈니스용 Skype에서 로그인 중에 사용할 전송 및 서버를 식별 하는 방법을 지정 합니다. 이 설정에서 다음을 지정 합니다. <br/>  Serveraddres외부 방화벽 외부에서 연결 하는 경우 클라이언트 및 페더레이션된 대화 상대에 사용 되는 서버 이름 또는 IP 주소를 지정 합니다. <br/>  ServerAddressInternal: 클라이언트가 조직의 방화벽 내부에서 연결할 때 사용 되는 서버 이름 또는 IP 주소를 지정 합니다. <br/>  전송: TCP (전송 제어 프로토콜) 또는 TLS (전송 계층 보안) 중 하나를 지정 합니다. <br/> |
|지원 되는 추가 서버 버전 (ConfiguredServerCheckValues)  <br/> |비즈니스용 Skype Server가 로그온 할 때 기본적으로 지원 되는 서버 버전 외에 세미콜론으로 구분 된 서버 버전 이름 목록을 지정 합니다.  <br/> |
|로그인 실패 로그 (Disableautomatic Sendtracing)의 자동 업로드 사용 안 함  <br/> |분석을 위해 비즈니스용 Skype Server에 로그인 오류 로그를 자동으로 업로드 합니다. 로그인에 성공 하면 로그가 자동으로 업로드 되지 않습니다. 이 정책이 구성 되지 않은 경우 다음이 수행 됩니다.  <br/> 비즈니스용 Skype Online 사용자: 로그인 실패 로그가 자동으로 업로드 됩니다. 비즈니스용 Skype 온-프레미스 사용자: 업로드 하기 전에 사용자에 게 확인 대화 상자가 표시 됩니다. 이 설정을 사용 하지 않으면 로그인 로그가 비즈니스용 skype Server에 자동으로 업로드 되며 비즈니스용 skype 온-프레미스 및 비즈니스용 Skype Online 사용자가 모두 가능 합니다. 이 설정을 사용 하면 로그인 로그가 자동으로 업로드 되지 않습니다.  <br/> |
|SIP 연결에 대 한 HTTP 대체 사용 안 함 (DisableHttpConnect)  <br/> |TLS 또는 TCP를 사용할 수 없는 경우 비즈니스용 Skype 서버가 HTTP를 사용 하 여 서버에 연결을 시도 하지 못하도록 합니다. 기본적으로 비즈니스용 Skype는 TLS 또는 TCP를 사용 하 여 서버에 대 한 연결을 시도 하 고, 이러한 전송 방법 모두에 성공 하지 못하면 비즈니스용 Skype에서 HTTP를 사용 하 여 연결을 시도 합니다. 대체 HTTP 연결 시도를 사용 하지 않도록 설정 하려면이 정책을 사용 합니다.  <br/> |
|로그온 자격 증명 필요 (DisableNTCredentials)  <br/> |사용자가 SIP 서버에 로그인 하는 동안 자동으로 Windows 자격 증명을 사용 하는 대신 비즈니스용 Skype에 대 한 로그온 자격 증명을 제공 해야 합니다.  <br/> |
|DisableServerCheck (서버 버전 검사) 사용 안 함  <br/> |이 정책을 1로 설정 하는 경우 비즈니스용 Skype가 로그인 하기 전에 서버 이름 및 버전을 확인 하는 것을 방지 합니다. 기본적으로 비즈니스용 Skype는 로그인 하기 전에 이러한 검사를 수행 합니다.  <br/> |
|BITS를 사용 하 여 주소록 서비스 파일 다운로드 (EnableBitsForGalDownload)를 사용 하도록 설정  <br/> |비즈니스용 Skype에서 BITS (Background Intelligent Transfer Service)를 사용 하 여 주소록 서비스 파일을 다운로드할 수 있습니다.  <br/> |
|SIP 보안 모드 구성 (EnableSIPHighSecurityMode)  <br/> |비즈니스용 Skype에서 인스턴트 메시지를 보다 안전 하 게 보내고 받을 수 있습니다. 이 정책은 Windows .NET 또는 Microsoft Exchange Server 서비스에는 적용 되지 않습니다.  <br/> 이 정책 설정을 구성 하지 않으면 비즈니스용 Skype에서 모든 전송을 사용할 수 있습니다. 그러나 TLS를 사용 하지 않고 서버에서 사용자를 인증 하는 경우 비즈니스용 Skype는 NTLM 또는 Kerberos 인증을 사용 해야 합니다.  <br/> |
|전체 주소록 다운로드 초기 지연 (GalDownloadInitialDelay)  <br/> |GAL (전체 주소 목록)을 다운로드할 때 까지의 기간을 지정 합니다. 기본값은 60 분으로, 서버는 GAL 파일의 다운로드가 0 ~ 60 분 사이인 임의 기간에 대해 지연 됨을 의미 합니다.  <br/> |
|사용자가 비즈니스용 Skype (PreventRun)를 실행 하지 못하도록 방지  <br/> |사용자가 비즈니스용 Skype를 실행할 수 없습니다. 컴퓨터 구성 및 사용자 구성에서이 정책 설정을 구성할 수 있지만 컴퓨터 구성 아래의 정책 설정이 우선권을 갖습니다.  <br/> |
|사용자 암호 저장 허용 (SavePassword)  <br/> |비즈니스용 Skype가 비밀 번호를 저장할 수 있도록 합니다.  <br/> |
|SIP 압축 모드 구성 (SipCompression)  <br/> |SIP 압축을 켤 시기를 지정 합니다. 기본적으로 SIP 압축은 어댑터 속도에 따라 사용 하도록 설정 됩니다. 이 정책을 설정 하면 로그인 시간이 늘어날 경우에 유의 해야 합니다.  <br/> |
|신뢰할 수 있는 도메인 목록 (TrustModelData)  <br/> |고객 SIP 도메인의 접두사와 일치 하지 않는 신뢰할 수 있는 도메인이 나열 됩니다.  <br/> |
   
서버에 구성 된 정책은 그룹 정책 설정 및 사용자가 구성한 클라이언트 옵션 보다 우선 합니다. 다음 표에서는 충돌이 발생할 경우 설정이 우선 하는 순서를 요약 하 여 설명 합니다.
  
**그룹 정책 우선 순위**

|**우선적**|**설정 위치 또는 방법**|
|:-----|:-----|
|raid-1  <br/> |비즈니스용 Skype Server 대역내 프로비저닝  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3-4  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4(tcp/ipv4)  <br/> |비즈니스용 Skype의 옵션 대화 상자  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>비즈니스용 Skype 관리 서식 파일을 사용 하 여 그룹 정책 설정을 정의 하려면

1. 모든 언어 중립적인 ADMX 파일을 포함할 루트 수준의 폴더를 만듭니다. 예를 들어이 위치에서 도메인 컨트롤러에 중앙 저장소의 루트 폴더를 만듭니다.
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 이 절차에서는 도메인의 여러 컴퓨터를 관리 한다고 가정 합니다. 이 경우 주 도메인 컨트롤러의 Sysvol 폴더에 있는 중앙 저장소에 템플릿을 저장 합니다. 이는 도메인 관리 템플릿에 대해 복제 된 중앙 저장소 위치를 제공 합니다. 
  
2. 사용할 각 언어에 대 한 하위 폴더를 만듭니다. 이러한 하위 폴더에 언어별 ADML 리소스 파일이 포함 됩니다. 예를 들어이 위치에 미국 영어 (EN-US)의 하위 폴더를 만듭니다.
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

