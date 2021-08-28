---
title: 웹 서비스 구성 설정 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '요약: 웹 서비스 구성 설정을 관리하기 비즈니스용 Skype 서버.'
ms.openlocfilehash: f007a93eb71fc015f71ddef51011008315de82e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633612"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>웹 서비스 구성 설정 비즈니스용 Skype 서버
 
**요약:** 웹 서비스 구성 설정 관리 비즈니스용 Skype 서버.
  
웹 서비스 페이지를 **사용하여** 관련 웹 서버 및 웹 서비스에 액세스하는 비즈니스용 Skype 서버 방법을 구성할 수 있습니다.
  
다음 단계에 따라 새 웹 서비스 정책을 만들 수 있습니다.
  
### <a name="to-create-new-web-service-configuration-settings"></a>새 웹 서비스 구성 설정을 만들하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 표시줄에서 **보안**, **웹 서비스** 를 차례로 클릭합니다.
    
4. **웹 서비스** 페이지에서 **새로 만들기** 를 클릭하고 다음 중 하나를 수행합니다.
    
   - 사이트에 대해 웹 서비스를 구성하려면 **사이트 구성** 을 클릭합니다. **사이트 선택** 에서 웹 서비스 정책을 적용할 사이트를 클릭하고 **확인** 을 클릭합니다.
    
   - 풀에 대해 웹 서비스를 구성하려면 **풀 구성** 을 클릭합니다. **서비스 선택** 에서 웹 서비스 정책을 적용할 서비스를 클릭하고 **확인** 을 클릭합니다. 
    
5. **새 웹 서비스 설정** 의 **통합 Windows 인증** 에서 **협상**, **통합 Windows 인증** 또는 **없음** 중 하나를 선택합니다.
    
6. 환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.
    
   - **PIN 인증 사용** - PIN 번호를 사용하여 클라이언트를 인증합니다.
    
   - **인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.
    
   - **인증서 체인 다운로드 사용** - 인증 인증서가 있는 서버에서 해당 인증서에 대해 인증서 체인을 다운로드하도록 합니다
    
7. **커밋** 을 클릭합니다.
    
## <a name="modify-existing-web-service-configuration-settings"></a>기존 웹 서비스 구성 설정 수정

웹 서비스 페이지를 **사용하여** 관련 웹 서버 및 웹 서비스에 액세스하는 비즈니스용 Skype 서버 방법을 구성할 수 있습니다.
  
다음 단계에 따라 기존의 웹 서비스 정책을 수정할 수 있습니다.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>기존 웹 서비스 구성 설정을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 표시줄에서 **보안**, **웹 서비스** 를 차례로 클릭합니다.
    
4. **웹 서비스** 페이지에서 구성을 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.
    
5. 웹 **서비스 설정** 편집의 통합 Windows **인증에서** 협상, 통합 Windows **인증** 또는 없음을 **선택합니다.** 
    
6. 환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.
    
   - **PIN 인증 사용** - PIN 번호를 사용하여 클라이언트를 인증합니다.
    
   - **인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.
    
   - **인증서 체인 다운로드 사용** - 인증 인증서가 있는 서버에서 해당 인증서에 대해 인증서 체인을 다운로드하도록 합니다
    
7. **커밋** 을 클릭합니다.
    
## <a name="delete-existing-web-service-configuration-settings"></a>기존 웹 서비스 구성 설정 삭제

다음 단계에 따라 웹 서비스 구성 설정을 삭제합니다.
  
### <a name="to-delete-web-service-configuration-settings"></a>웹 서비스 구성 설정을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 표시줄에서 **보안**, **웹 서비스** 를 차례로 클릭합니다.
    
4. **웹 서비스** 페이지의 검색 필드에 삭제할 정책의 이름 일부나 전체를 입력합니다.
    
5. 정책 목록에서 원하는 정책을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.
    
6. **확인** 을 클릭합니다.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Cmdlet을 사용하여 웹 설정 구성 Windows PowerShell 삭제

웹 서비스 구성 설정은 Windows PowerShell **Remove-CsWebServiceConfiguration** cmdlet을 사용하여 삭제할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 서버를 사용하여 Windows PowerShell 연결하는 비즈니스용 Skype 서버 ["빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)블로그 문서를 참조하십시오. 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>웹 서비스 구성 설정의 특정 컬렉션을 삭제하려면

- 다음 명령은 Redmond 사이트에 적용된 웹 서비스 보안 설정을 제거합니다.
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 웹 서비스 구성 설정을 삭제하려면

다음 명령은 서비스 범위에 적용된 모든 웹 서비스 보안 설정을 제거합니다.
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>인증서 인증을 허용하는 모든 웹 서비스 구성 설정을 삭제하려면

다음 명령은 인증서 인증을 사용할 수 있도록 허용하는 모든 웹 서비스 보안 설정을 제거합니다.
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

자세한 내용은 [Remove-CsWebServiceConfiguration을 참조합니다.](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)
