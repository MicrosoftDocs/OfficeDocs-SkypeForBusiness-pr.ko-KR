---
title: '비즈니스용 Skype 서버: Active Directory 준비'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '요약: Active Directory 도메인을 설치하기 위해 Active Directory 도메인을 준비하는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: fbc5769c38436cdc7199aadf4338fa59a47edf3d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845861"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>비즈니스용 Skype 서버: Active Directory 준비
 
**요약:** Active Directory 도메인을 설치하기 위해 Active Directory 도메인을 준비하는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 비즈니스용 Skype 서버 [평가판을 다운로드합니다.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
비즈니스용 Skype 서버 Active Directory와 긴밀하게 작동합니다. Active Directory 도메인에서 작업할 수 있는 Active Directory 도메인을 준비해야 비즈니스용 Skype 서버. 이 프로세스는 배포 마법사에서 수행하며 도메인에 대해 한 번만 수행됩니다. 이는 프로세스에서 그룹을 만들고 도메인을 수정하기 때문에 이 작업을 한 번만 해야 합니다. 1~5단계는 순서에 따라 수행하면 됩니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로 6, 7, 8단계를 순서대로 수행해야 합니다. Active Directory 준비는 8단계 중 4단계입니다. Active Directory 계획에 대한 자세한 내용은 [2019년](../../../SfBServer2019/plan/system-requirements.md)비즈니스용 Skype 서버 서버 요구 사항에 대한 환경 요구 사항을 비즈니스용 Skype 서버 참조하세요. [](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
  
![개요 다이어그램.](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory 준비

비즈니스용 Skype 서버 AD DS(Active Directory 도메인 서비스)와 긴밀하게 통합됩니다. 처음 비즈니스용 Skype 서버 설치하려면 Active Directory를 준비해야 합니다. Active Directory 준비 배포 마법사의 섹션에서는 Active Directory 환경이 Active **Directory와** 함께 사용할 수 비즈니스용 Skype 서버.
  
> [!NOTE]
> 비즈니스용 Skype 서버(AD DS)를 사용하여 토폴로지의 모든 서버를 추적하고 통신합니다. 이러한 서버의 대부분이 도메인에 가입되어 있어야 서버가 제대로 비즈니스용 Skype 서버 수 있습니다. Edge 및 역방향 프록시와 같은 서버는 도메인에 가입되어 있지 않습니다.
  
> [!IMPORTANT]
> Active Directory 준비 절차는 배포의 각 도메인에 대해 한 번만 실행해야 합니다. 
  
Active Directory 준비에 대한 **비디오 단계를 시청하세요.**
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>배포 마법사에서 Active Directory 준비

1. Active Directory 도메인에 대한 Schema Admins 자격 증명을 사용하여 사용자로 로그온합니다.
    
2. 배포 비즈니스용 Skype 서버 열기.
    
    > [!TIP]
    > 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토하려면 배포 마법사를 실행한 컴퓨터에서 해당 단계를 실행한 AD DS 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다. 예를 들어 사용자가 도메인 contoso.local에서 도메인 관리자로 로그온한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다. 
  
3. Active **Directory 준비 링크를** 클릭합니다.
    
4. **1단계: 스마마 준비**
    
    a. 1단계 제목 아래의 드롭다운을 클릭하여 액세스할 수 있는 1단계의 선행 준비 정보를 검토합니다.
    
    b. **1단계에서** 실행을 클릭하여 Schema 준비 마법사를 실행합니다.
    
    c. 이 절차는 각 배포에 대해 한 번만 실행하고 다음 을 **클릭합니다.**
    
    d. 스마마가 준비된 후 로그 보기 를 클릭하여 **로그를 볼 수 있습니다.** 
    
    e. **마쳤습니다를** 클릭하여 준비 Schema 마법사를 닫고 Active Directory 준비 단계로 돌아온다.
    
5. **2단계: Schema 파티션 복제 확인**
    
    a. 도메인의 도메인 컨트롤러에 로그온합니다.
    
    b. 서버 관리자의 도구  드롭다운 메뉴에서 **ADSI** **편집을 열 수 있습니다.**
    
    c. **동작** 메뉴에서 **연결** 을 클릭합니다.
    
    d. **잘 알려진 명명 컨텍스트를 선택합니다** 아래에 있는 **연결 설정** 대화 상자에서 **스키마** 를 선택한 다음 **확인** 을 클릭합니다.
    
    e. Schema 컨테이너에서 **CN=ms-RTC-SIP-SchemaVersion** 을 검색합니다. 이 개체가 존재하고 **rangeUpper** 특성 값이 1150이고 **rangeLower** 특성 값이 3이면 해당 스마가 성공적으로 업데이트 및 복제되었습니다. 이 개체가 존재하지 않는 경우 **또는 rangeUpper** 및 **rangeLower** 특성의 값이 지정되지 않은 경우 해당 스마가 수정되지 않은 것이거나 복제되지 않은 것입니다.
    
6. **3단계: 현재 포리스트 준비**
    
    a. 3단계 제목 아래의 드롭다운을 클릭하여 액세스할 수 있는 3단계의 선행 준비 정보를 검토합니다.
    
    b. **3단계에서** 실행을 클릭하여 현재 포리스트 준비 마법사를 실행합니다.
    
    c. 이 절차는 배포당 한 번만 실행하고 다음 을 **클릭합니다.**
    
    d. 유니버설 그룹을 만들 도메인을 지정합니다. 서버가 도메인의 일부인 경우 로컬 도메인 **을** 선택하고 다음 을 **클릭할 수 있습니다.**
    
    e. 포리스트가 준비된 후 로그 보기 를 클릭하여 **로그를 볼 수 있습니다.** 
    
    f. **마친을** 클릭하여 현재 포리스트 준비 마법사를 닫고 Active Directory 준비 단계로 돌아온다.
    
    g. 앱 **비즈니스용 Skype 서버 관리 셸을** 클릭하여 PowerShell을 실행합니다. 
    
    h. Get-CsAdForest 명령을 입력하고 **Enter를 누르고 를 입력합니다.**
    
    i. 결과가 LC_FORESTSETTINGS_STATE_READY **그림과** 같이 포리스트가 준비된 것입니다.
    
     ![포리스트 복제를 검증합니다.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **4단계: 글로벌 카탈로그 복제 확인**
    
    a. 포리스트 준비가 실행된 포리스트의 도메인 컨트롤러(가급적이면 다른 도메인 컨트롤러의 원격 사이트)에서 **Active Directory 사용자 및 컴퓨터** 를 엽니다.
    
    b. **Active Directory 사용자 및 컴퓨터** 에서 포리스트 또는 자식 도메인의 도메인 이름을 확장합니다.
    
    c. 왼쪽 창에서 **사용자** 컨테이너를 클릭하고 오른쪽 창에서 유니버설 그룹 **CsAdministrator를** 검색합니다. Cs로 시작하는 다른 새 유니버설 그룹 중 CsAdministrator가 있는 경우 Active Directory 복제가 성공한 것입니다.
    
    d. 그룹이 아직 없는 경우 복제를 강제로 진행하거나 15분간 기다렸다가 오른쪽 창을 새로 고칠 수 있습니다. 그룹이 나타나면 복제가 완료된 것입니다.
    
8. **5단계: 현재 도메인 준비**
    
    a. 5단계의 선행 준비 정보를 검토합니다.
    
    b. **5단계에서** 실행을 클릭하여 현재 도메인 준비 마법사를 실행합니다.
    
    c. 이 절차는 배포의 각 도메인에 대해 한 번만 실행하고 다음 을 **클릭합니다.**
    
    d. 도메인이 준비된 후 로그 보기 를 클릭하여 **로그를 볼 수 있습니다.** 
    
    e. **마쳤습니다를** 클릭하여 현재 도메인 준비 마법사를 닫고 Active Directory 준비 단계로 돌아온다.
    
    이러한 단계는 비즈니스용 Skype 서버 있는 모든 도메인에서 완료해야 합니다. 그렇지 않으면 서비스가 시작되지 않을 수 있습니다. 여기에는 사용자, 연락처 개체, 관리 그룹 또는 다른 유형의 개체와 같은 모든 유형의 Active Directory 개체가 포함됩니다. -Set-CsUserReplicatorConfiguration -ADDomainNamingContextList를 사용하여 필요한 경우 비즈니스용 Skype 서버 도메인만 추가할 수 있습니다.
    
9. **6단계: 도메인에서 복제 확인**
    
    a. 앱 **페이지에서 비즈니스용 Skype 서버** 관리 셸을 클릭하여 PowerShell을 실행합니다. 
    
    b. 명령줄을 Get-CsAdDomain 도메인 내에서 복제를 확인할 수 있습니다.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Domain 매개 변수를 지정하지 않으면 값이 로컬 도메인으로 설정됩니다. 
  
    contoso.local 도메인에 대한 명령을 실행하는 예:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > GlobalSettingsDomainController 매개 변수를 사용하여 전역 설정이 저장되는 위치를 나타낼 수 있습니다. 설정이 시스템 컨테이너에 저장되어 있는 경우(전역 설정이 구성 컨테이너로 마이그레이션되지 않은 업그레이드 배포에서 일반적) AD DS 포리스트의 루트에서 도메인 컨트롤러를 정의합니다. 전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다. 이 매개 변수를 지정하지 않으면 이 cmdlet은 설정이 구성 컨테이너에 저장되고 Active Directory의 도메인 컨트롤러를 참조하는 것으로 가정합니다. 
  
    c. 결과가 LC_DOMAINSETTINGS_STATE_READY **도메인이** 복제된 것입니다.
    
10. **7단계: 사용자 추가를 통해 비즈니스용 Skype 서버 제어판에 대한 관리 액세스 권한 제공**
    
    a. Domain Admins 그룹 또는 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.
    
    b. **Active Directory 사용자** 및 컴퓨터를 열고  도메인을 확장하고 사용자 컨테이너를 클릭한 다음 CSAdministrator를 마우스 오른쪽 단추로 클릭하고 **속성을 클릭합니다.**
    
    c. **CSAdministrator 속성** 에서 **구성원** 탭을 클릭합니다.
    
    d. **구성원** 탭에서 **추가** 를 클릭합니다. 사용자, **연락처, 컴퓨터, 서비스 계정** 또는 그룹 선택에서 선택할 개체 이름 입력을 **찾습니다.** CSAdministrators 그룹에 추가할 사용자 이름 또는 그룹 이름을 입력합니다. **확인** 을 클릭합니다.
    
    e. 구성원 **탭에서** 선택한 사용자 또는 그룹이 존재 하는지 확인 합니다. **확인** 을 클릭합니다.
    
    > [!CAUTION]
    > 비즈니스용 Skype 서버 제어판은 역할 기반 액세스 제어 도구입니다. CsAdministrator 그룹의 구성원 자격은 사용 가능한 모든 구성 기능에 대한 비즈니스용 Skype 서버 제어판을 사용하는 사용자에게 제공됩니다. 특정 기능에 대해 디자인된 사용 가능한 다른 역할도 있습니다. 사용 가능한 역할에 대한 자세한 내용은 [2019년](../../../SfBServer2019/plan/system-requirements.md)비즈니스용 Skype 서버 서버 요구 사항에 대한 환경 요구 사항을 비즈니스용 Skype 서버 참조하세요. [](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 사용자가 관리 그룹의 구성원으로 비즈니스용 Skype 서버 사용자를 사용하도록 설정하지는 않습니다. 
  
    > [!CAUTION]
    > 보안 및 역할 기반 액세스 제어 무결성을 유지하도록 지원하기 위해 사용자가 보안 배포를 관리하기 위해 수행하는 역할을 정의하는 그룹에 사용자를 비즈니스용 Skype 서버 합니다. 
  
11. 로그오프했다가 새 Windows 보안 그룹으로 보안 토큰이 업데이트될 수 있도록 비즈니스용 Skype 서버 로그온한 다음 배포 마법사를 다시 니다.
    
12. 그림과 같이 **Active Directory** 준비 옆에 성공 여부를 확인하는 녹색 확인 표시가 표시되는지 확인합니다.
    
     ![Active Directory 준비 완료](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>참고 항목
 
[2015용 Active Directory 비즈니스용 Skype 서버 서비스](../../plan-your-deployment/security/active-directory-domain-services.md)
