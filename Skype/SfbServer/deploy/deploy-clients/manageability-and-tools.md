---
title: Skype 룸 시스템 관리 가능성 및 도구
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 이 항목을 읽고 Skype 룸 시스템의 관리 도구에 대해 자세히 알아보습니다.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805798"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 룸 시스템 관리 가능성 및 도구
 
이 항목을 읽고 Skype 룸 시스템의 관리 도구에 대해 자세히 알아보습니다.
  
## <a name="administrative-portal"></a>관리 포털

비즈니스용 Skype 서버의 경우 비즈니스용 Skype 시스템 관리 포털을 사용하여 조직 내에서 Skype 룸 시스템 배포를 적극적으로 관리하고 모니터링할 수 있습니다.
  
자세한 내용은 다음 문서를 참조하세요.
  
- [비즈니스용 Skype 서버에서 SRS v1 관리 웹 포털 배포](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange 검사 목록

- 자동 업데이트가 설정되어 있으며 내부 DNS A/CNAME 레코드를 사용할 수 autodiscover.domain.com.
    
- Ping autodiscover(예: Ping Autodiscover.contoso.com).
    
- Microsoft 연결 분석기 도구를 사용하여 자동 검색 서비스를 테스트합니다. 첫 번째 테스트인 "Office Outlook에 로그온할 수 없습니다."를 선택 합니다.
    
- 회의실에 리소스 사서함이 이미 있는 경우 Skype 룸 시스템에 대해 이 계정을 확장합니다(예: 페이지 아래쪽의 스크립트).
    
## <a name="skype-for-business-checklist"></a>비즈니스용 Skype 검사 목록

- 다음 도구를 실행합니다.
    
  - 비즈니스용 Skype 모범 사례 분석기     
  - 비즈니스용 Skype 상태 분석 도구(Excel)    
  - Business Connectivity용 Skype 분석기 32비트 또는 64비트
    
- [Office 365의](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)유용한 새 문제 해결 및 분석 도구를 검토합니다. 비즈니스용 Skype 풀과 Office Web Apps 서버가 있으며 비즈니스용 Skype 클라이언트를 사용하여 PowerPoint 데크를 공유할 수 있습니다.
    
- 회의실에 리소스 사서함이 이미 있는 경우 비즈니스용 Skype에 사용하도록 설정하세요.
    
- 필요한 경우 회의실 시스템에 DID(전화 번호)를 요청하고 Active Directory 도구에서 일반 전화 필드를 업데이트합니다.
    
## <a name="network"></a>네트워크

- Skype 룸 시스템에 대한 유선 네트워크 연결이 있는지 확인합니다.
    
- 비즈니스용 Skype에 대한 네트워크 계획 가이드를 읽어보세요.
    
- 비즈니스용 Skype 파트너에게 비즈니스용 Skype 네트워크 평가를 요청합니다.
    
- 비즈니스용 Skype 상태 분석 도구(Excel)에서 캡처한 성능 데이터를 읽어 읽습니다.
    
- 네트워크 분석 도구를 실행합니다.
    
- 사전 통화 진단 도구를 실행합니다.
    
## <a name="skype-room-system-security"></a>Skype 룸 시스템 보안

Skype 룸 시스템은 비즈니스용 Skype 보안 모델, 권한 관리 및 SCOM과 같은 관리 도구를 사용하여 Windows 배포에 완전히 통합할 수 있는 포함된 시스템입니다. 기능은 다음과 같습니다.
  
- 사용자 모드에서 디스크 쓰기를 방지하는 쓰기 필터 
    
- 권한이 없는 앱이 실행되지 않도록 하는 앱 보관 모든 USB 포트는 사용자 모드에서 사용하지 않도록 설정됩니다.
    
  - Skype 룸 시스템 하드웨어에는 표준 앱이나 뷰어가 없습니다. 모든 콘텐츠는 HTTP 또는 RDP 프로토콜을 통해 렌더링됩니다.
    
  - 어플라이언스 PC는 Windows Embedded Standard 7 운영 체제를 실행합니다. 장치를 포함한 모든 하드웨어는 OEM 파트너가 제공합니다.
    
  - AD DS(Active Directory 도메인 서비스)에 대한 선택적 도메인 가입으로 로컬 보안 계정 관리 및 제어를 사용하도록 설정
    
- 비즈니스용 Skype 관리 센터를 사용하여 로컬 관리자 계정을 관리할 수도 있습니다.
    
- Skype 룸 시스템은 표준 Microsoft 업데이트 프로세스를 통해 업데이트됩니다.
    
- Skype 룸 시스템은 비즈니스용 Skype와 연결됩니다.
    
  - 비즈니스용 Skype는 모든 통신 모드에 종단 간 암호화 및 권한 부여를 사용합니다.
    
  - Skype 룸 시스템은 비즈니스용 Skype 보안 및 규정 준수 표준을 지원합니다. 자세한 [내용은 비즈니스용 Skype 서버의 보안](../../plan-your-deployment/security/security.md) 계획을 참조하세요.
    
## <a name="license"></a>License

소프트웨어를 정비하는 데 KMS를 사용하는지 확인해야 합니다. 이 경우 비즈니스용 Skype 클라이언트 KMS 키를 확인하거나 추가해야 할 수 있습니다. KMS를 사용하지 않는 경우 비즈니스용 Skype 클라이언트 MAK에 대한 볼륨 라이선스 키를 요청합니다.
  
## <a name="license-keys"></a>라이선스 키

Skype 룸 시스템은 백그라운드에서 비즈니스용 Skype 데스크톱 클라이언트를 실행합니다. Skype 룸 시스템이 도메인 구성원인 경우 KMS를 검색합니다. 볼륨 라이선스 KMS 키가 있는 경우 자동으로 정품 인증됩니다. 볼륨 라이선스는 xxxxx-xxxxx-xxx-xx-xxx를 표시하는 MAK도 제공합니다. MAK를 사용하여 정품 인증하려면 인터넷에 연결해야 하지만 KMS는 정품 인증하지 않습니다. 자세한 내용은 Office 2013의 볼륨 정품 인증을 참조하세요.
  
- MAK 키를 입력하려면 OEM 설정 SRS 라이선스 \> 도구로 이동합니다. 상태 확인을 클릭합니다. 상태가 "제품이 정품 인증되지 않았습니다."라는 표시가 표시되면 키를 입력합니다.
    
- 정품 인증 중에 "'소프트웨어 라이선스 서비스에서 제품 키가 잘못 보고되었습니다."라는 오류가 표시될 경우 다음을 확인합니다.
    
  - 키를 올바르게 입력했습니다.
    
  - 다른 키가 아니라 비즈니스용 Skype MAK 키를 입력한 경우
    
  - 시스템에 인터넷에 액세스할 수 있습니다.
    
- 전화를 통해 정품 인증할 수 있지만 먼저 SRS 라이선스 도구를 사용하여 정품 인증을 시도해야 합니다. 전화를 통해 정품 인증하려면 테스트 모임을 시작하십시오(테스트 통화가 너무 짧지 않은 경우). Office 정품 인증 마법사에서 전화 정품 인증을 선택하고 Microsoft에 전화를 걸고 긴 번호를 입력한 다음 응답을 입력합니다.
    
## <a name="certificate-authority"></a>인증 기관

Office Web Apps Server 2013 인증서를 발급하는 데 사용된 인증 기관에 인증서 해지 목록 속성에 HTTP 경로가 포함되어 있는지 확인
  
비즈니스용 Skype 서버를 사용하는 경우 인증서 파일(.crt)을 Skype 채팅방 시스템으로 가져오기 CA 서버의 CertEnroll 공유 또는 도메인에 가입된 PC의 신뢰할 수 있는 루트 폴더에서 쉽게 얻을 수 있습니다.
  
## <a name="certificates"></a>인증서

인증 기관에 인증서 해지 목록에 대한 http 경로가 있는지 확인 그렇지 않은 경우 CA를 포함하게 업데이트합니다.
  
시스템 설정 인증서 관리자에서 Skype 룸 시스템의 관리자 설정에 \> 인증서를 설치합니다. 내부 인증서에 대한 엔터프라이즈 루트 CA가 필요합니다.
  
필요한 인증서를 얻는 한 가지 방법은 인증서를 발급한 CA를 검색하는 것입니다. 비즈니스용 Skype 서버의 경우 비즈니스용 Skype의 PC에서 설정 도구 전화 접속 \> \> 회의 설정을 클릭합니다. 이렇게하면 내부 인증서를 발급한 CA에 의해 보안된 웹 페이지가 열립니다. 브라우저 주소 표시줄에서 잠금 아이콘을 클릭하여 보안 보고서를 표시합니다. 인증서 보기를 클릭하고 CRL 배포 지점 속성을 검사합니다. 두 번째 CN 매개 변수는 CA의 서버 이름입니다. 이제 Windows 탐색기에서 이 주소 \\ \< CA Server Name \> \CertEnroll을 니다. 두 .crl 파일과 .crt 파일을 플래시 드라이브에 복사하고 스마트 보드의 왼쪽에 넣습니다.
  
신뢰할 수 있는 방 인증 기관 폴더의 Skype 채팅방 시스템으로 .crt 파일을 가져올 수 있습니다.
  
Skype 채팅방 시스템에서 중간 인증 기관 폴더의 .crl 파일을 가져올 수 있습니다. 파일을 확인하려면 인증서 관리자의 파일 확장명 필터를 .crl로 변경해야 합니다.
  
참고: Office Web Apps 2013 서버는 비즈니스용 Skype와 동일한 CA를 공유할 수 있습니다. 그렇지 않은 경우 모임에서 PowerPoint를 공유할 수 없습니다. 위에서 설명한 대로 IT에 확인하고 CA 네트워크 공유 CertEnroll에서 CRT 및 CRL 파일을 얻습니다. 
  
도메인 멤버 자격은 Skype 룸 시스템을 Windows 시스템으로 취급하고 일부 인증서 측면에 대해 Active Directory를 사용할 수 있기 때문에 몇 가지 작업을 단순화할 수 있습니다. 그러나 수동으로 관리하는 것이 가장 좋은 것입니다.
  

