---
title: 비즈니스용 Skype 서버에서 웹 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '요약: 비즈니스용 Skype 서버에서 웹 서비스 구성 설정을 관리 합니다.'
ms.openlocfilehash: 383b85e156dfdbc6af7606da49d4cf89bf655698
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991933"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 웹 서비스 구성 설정 관리
 
**요약:** 비즈니스용 Skype 서버의 웹 서비스 구성 설정을 관리 합니다.
  
**웹 서비스** 페이지를 사용 하 여 비즈니스용 Skype 서버 관련 웹 서버 및 웹 서비스에 액세스 하는 인증 방법을 구성할 수 있습니다.
  
새 웹 서비스 정책을 만들려면 다음 단계를 따르세요.
  
### <a name="to-create-new-web-service-configuration-settings"></a>새 웹 서비스 구성 설정을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.
    
4. **웹 서비스** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
   - 사이트에 대 한 웹 서비스를 구성 하려면 **사이트 구성을**클릭 합니다. **사이트 선택**에서 웹 서비스 정책이 사이트를 적용 하는 사이트를 클릭 하 고 **확인**을 클릭 합니다.
    
   - 풀에 대 한 웹 서비스를 구성 하려면 **풀 구성을**클릭 합니다. **서비스 선택**에서 웹 서비스 정책이 적용 되는 서비스를 클릭 하 고 **확인**을 클릭 합니다. 
    
5. **새 웹 서비스 설정**에서 **windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**을 선택 합니다.
    
6. 해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.
    
   - Pin **인증** 을 사용 하 여 클라이언트가 pin 번호를 사용 하 여 인증할 수 있도록 합니다.
    
   - **인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.
    
   - **인증서 체인 다운로드 사용** 인증 인증서를 사용 하 여 서버에 제공 되는 경우 해당 인증서의 인증서 체인을 다운로드 합니다.
    
7. **커밋**을 클릭합니다.
    
## <a name="modify-existing-web-service-configuration-settings"></a>기존 웹 서비스 구성 설정 수정

**웹 서비스** 페이지를 사용 하 여 비즈니스용 Skype 서버 관련 웹 서버 및 웹 서비스에 액세스 하는 인증 방법을 구성할 수 있습니다.
  
기존 웹 서비스 정책을 수정 하려면 다음 단계를 따르세요.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>기존 웹 서비스 구성 설정을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.
    
4. **웹 서비스** 페이지에서 구성을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **웹 서비스 편집 설정**의 **Windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**을 선택 합니다.
    
6. 해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.
    
   - Pin **인증** 을 사용 하 여 클라이언트가 pin 번호를 사용 하 여 인증할 수 있도록 합니다.
    
   - **인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.
    
   - **인증서 체인 다운로드 사용** 인증 인증서를 사용 하 여 서버에 제공 되는 경우 해당 인증서의 인증서 체인을 다운로드 합니다.
    
7. **커밋**을 클릭합니다.
    
## <a name="delete-existing-web-service-configuration-settings"></a>기존 웹 서비스 구성 설정 삭제

웹 서비스 구성 설정을 삭제 하려면 다음 단계를 따르세요.
  
### <a name="to-delete-web-service-configuration-settings"></a>웹 서비스 구성 설정을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.
    
4. **웹 서비스** 페이지의 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.
    
5. 정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
6. **확인**을 클릭합니다.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 웹 서비스 구성 설정 삭제

Windows PowerShell 및 **Remove CsWebServiceConfiguration** cmdlet을 사용 하 여 웹 서비스 구성 설정을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>웹 서비스 구성 설정의 특정 컬렉션을 삭제 하려면

- 다음 명령은 Redmond 사이트에 적용 된 웹 서비스 보안 설정을 제거 합니다.
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 웹 서비스 구성 설정을 삭제 하려면

다음 명령은 서비스 범위에 적용 된 모든 웹 서비스 보안 설정을 제거 합니다.
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>인증서 인증을 허용 하는 모든 웹 서비스 구성 설정을 삭제 하려면

다음 명령은 인증서 인증을 사용할 수 있는 모든 웹 서비스 보안 설정을 제거 합니다.
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

자세한 내용은 [제거-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)를 참조 하세요.
  

