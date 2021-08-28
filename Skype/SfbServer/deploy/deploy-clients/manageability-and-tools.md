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
ms.localizationpriority: medium
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 이 항목을 읽고 룸 시스템용 관리 Skype 대해 자세히 알아보습니다.
ms.openlocfilehash: 92fe780565728c457d6853e0210ec7981386ca0b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592882"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 룸 시스템 관리 가능성 및 도구
 
이 항목을 읽고 룸 시스템용 관리 Skype 대해 자세히 알아보습니다.
  
## <a name="administrative-portal"></a>관리 포털

비즈니스용 Skype 서버 배포의 경우 Skype Room System 관리 포털을 사용하여 조직 내의 Skype 배포를 적극적으로 관리하고 모니터링할 수 있습니다.
  
자세한 내용은 다음 문서를 참조하세요.
  
- [SRS v1 관리 웹 포털을 비즈니스용 Skype 서버](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange 검사 목록

- 자동iscover가 설정되어 있으며 내부 DNS A/CNAME 레코드를 사용할 수 autodiscover.domain.com.
    
- Ping autodiscover(예: Ping Autodiscover.contoso.com).
    
- Microsoft 연결 분석기 도구를 사용하여 자동 검색 서비스를 테스트합니다. 첫 번째 테스트인 "사용자 계정으로 로그온할 Office Outlook."
    
- 회의실에 이미 리소스 사서함이 있는 경우 Skype 회의실 시스템(페이지 아래쪽의 스크립트 예)에 대해 이 계정을 확장합니다.
    
## <a name="skype-for-business-checklist"></a>비즈니스용 Skype 검사 목록

- 다음 도구를 실행합니다.
    
  - 비즈니스용 Skype 모범 사례 분석기     
  - 비즈니스용 Skype 상태 분석 도구(Excel)    
  - 비즈니스용 Skype 연결 분석기 32비트 또는 64비트
    
- 에 대한 유용한 새 문제 해결 및 분석 [도구를 Office 365.](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365) 비즈니스용 Skype 및 Office Web Apps 서버가 있으며 PowerPoint 클라이언트를 사용하여 PowerPoint 수 비즈니스용 Skype 있습니다.
    
- 회의실에 이미 리소스 사서함이 있는 경우 리소스 사서함을 사용하도록 비즈니스용 Skype.
    
- 필요한 경우 미팅룸 System에 대해 DID(전화 번호)를 요청하고 Active Directory 도구에서 일반 전화 필드를 업데이트합니다.
    
## <a name="network"></a>네트워크

- 룸 시스템에 대한 유선 네트워크 Skype 확인합니다.
    
- 네트워크 계획 가이드를 비즈니스용 Skype.
    
- 파트너에게 비즈니스용 Skype 네트워크 평가를 비즈니스용 Skype 요청합니다.
    
- 비즈니스용 Skype 상태 분석 도구(Excel)에서 캡처한 성능 데이터를 Excel.
    
- 네트워크 분석 도구를 실행합니다.
    
- 사전 통화 진단 도구를 실행합니다.
    
## <a name="skype-room-system-security"></a>Skype Room System Security

Skype 룸 시스템은 SCOM과 같은 Windows, 권한 관리 및 관리 도구를 사용하여 비즈니스용 Skype 배포에 완전히 통합할 수 있는 포함된 시스템입니다. 기능은 다음과 같습니다.
  
- 사용자 모드에서 디스크 쓰기를 방지하는 쓰기 필터 
    
- 앱 보관 - 권한이 없는 앱이 실행되지 않도록 합니다. 모든 USB 포트는 사용자 모드에서 사용하지 않도록 설정됩니다.
    
  - 표준 앱 또는 뷰어는 Skype 하드웨어에 없습니다. 모든 콘텐츠는 HTTP 또는 RDP 프로토콜을 통해 렌더링됩니다.
    
  - 어플라이언스 PC는 Windows Standard 7 운영 체제를 실행합니다. 장치를 포함한 모든 하드웨어는 OEM 파트너가 제공합니다.
    
  - AD DS(Active Directory 도메인 서비스에 대한 선택적 도메인 가입)를 통해 로컬 보안 계정 관리 및 제어를 사용할 수 있습니다.
    
- 또한 관리 센터에서 로컬 관리자 계정을 관리할 비즈니스용 Skype 있습니다.
    
- Skype 방 시스템은 표준 Microsoft 업데이트 프로세스를 통해 업데이트됩니다.
    
- Skype Room System은 비즈니스용 Skype.
    
  - 비즈니스용 Skype 모든 통신 모드에 대해 종단 간 암호화 및 권한 부여를 사용합니다.
    
  - Skype 방 시스템은 보안 비즈니스용 Skype 규정 준수 표준을 지원합니다. 자세한 [내용은 비즈니스용 Skype 보안](../../plan-your-deployment/security/security.md) 계획을 참조하세요.
    
## <a name="license"></a>License

소프트웨어 정품 인증을 위해 KMS 확인 이 경우 클라이언트 클라이언트 비즈니스용 Skype 확인하거나 KMS 추가해야 할 수 있습니다. 클라이언트를 사용하지 않는 KMS 클라이언트 MAK에 대한 볼륨 비즈니스용 Skype 요청합니다.
  
## <a name="license-keys"></a>라이선스 키

Skype 방 시스템은 백그라운드에서 비즈니스용 Skype 데스크톱 클라이언트를 실행합니다. 룸 Skype 구성원이면 해당 도메인을 검색할 KMS. 볼륨 라이선싱 키가 있는 KMS 자동으로 정품 인증됩니다. 볼륨 라이선스는 xxxxx-xxxxx-xxx-xx-xxx를 표시하는 MAK도 제공합니다. MAK를 사용하여 정품 인증하려면 인터넷에 액세스해야 하지만 정품 인증을 KMS. 자세한 내용은 Volume activation of Office 참조하십시오.
  
- MAK 키를 입력하려면 OEM 설정 \> SRS 라이선스 도구로 이동하세요. 상태 확인을 클릭합니다. 상태가 "제품이 정품 인증되지 않았습니다."라고 표시되면 키를 입력합니다.
    
- 정품 인증 중에 "소프트웨어 라이선스 서비스에서 제품 키가 잘못 보고되었습니다."라는 오류가 표시될 경우 다음을 확인합니다.
    
  - 키를 올바르게 입력했습니다.
    
  - 다른 키가 비즈니스용 Skype MAK 키를 입력한 경우
    
  - 시스템에 인터넷에 액세스할 수 있습니다.
    
- 전화를 통해 정품 인증할 수 있지만 먼저 SRS 라이선스 도구를 사용하여 정품 인증을 시도해야 합니다. 전화를 통해 정품 인증하려면 테스트 모임을 시작해야 합니다(너무 짧은 테스트 통화 아미기). Office 정품 인증 마법사에서 전화 정품 인증을 선택하고 Microsoft에 전화를 걸고 긴 번호를 입력한 다음 응답을 입력합니다.
    
## <a name="certificate-authority"></a>인증 기관

인증서 해지 목록 속성에 Office Web Apps Server 2013 인증서를 발급하는 데 사용되는 인증 기관에 HTTP 경로가 포함되어 있는지 확인
  
인증서 파일을 사용하는 경우 인증서 파일(.crt)Skype 룸 시스템으로 비즈니스용 Skype 서버. CA 서버의 CertEnroll 공유 또는 도메인에 가입된 PC의 신뢰할 수 있는 루트 폴더에서 쉽게 얻을 수 있습니다.
  
## <a name="certificates"></a>인증서

인증 기관에 인증서 해지 목록에 대한 http 경로가 있는지 확인 그렇지 않은 경우 CA를 업데이트하여 CA를 포함합니다.
  
System 설정 Certificate Manager에서 Skype 룸 시스템의 관리자 설정에 \> 인증서를 설치합니다. 내부 인증서에 Enterprise 루트 CA가 필요합니다.
  
필요한 인증서를 얻는 한 가지 방법은 인증서를 발급한 CA를 검색하는 것입니다. 이 비즈니스용 Skype 서버 컴퓨터의 비즈니스용 Skype 전화 접속 회의 설정 \> \> 클릭합니다설정. 그러면 내부 인증서를 발급한 CA에 의해 보안된 웹 페이지가 열립니다. 브라우저 주소 표시줄에서 잠금 아이콘을 클릭하여 보안 보고서를 표시합니다. 인증서 보기를 클릭하고 CRL 배포 지점 속성을 검사합니다. 두 번째 CN 매개 변수는 CA의 서버 이름입니다. 이제 Windows \\ \< CA Server Name \> \CertEnroll에 대한 탐색기를 니다. 두 .crl 파일과 .crt 파일을 플래시 드라이브에 복사하고 SMART 보드의 왼쪽에 넣습니다.
  
.crt 파일을 신뢰할 수 있는 Skype 인증 기관 폴더의 Skype 시스템으로 가져와야 합니다.
  
중간 인증 기관 폴더의 Skype 룸 시스템의 .crl 파일을 가져올 수 있습니다. 파일을 확인하려면 인증서 관리자의 파일 확장명 필터를 .crl로 변경해야 합니다.
  
참고: Office Web Apps 2013 서버가 동일한 CA를 공유할 수 비즈니스용 Skype. 그렇지 않은 경우 모임에서 공유 PowerPoint 수 없는 것입니다. 위에서 설명한 대로 IT에 확인하고 CA 네트워크 공유 CertEnroll에서 CRT 및 CRL 파일을 얻습니다. 
  
도메인 멤버 자격은 Skype 룸 시스템을 Windows 수 있으며 일부 인증서 측면에 대해 Active Directory를 사용할 수 있기 때문에 일부 작업을 단순화할 수 있습니다. 그러나 수동으로 관리하는 것이 가장 좋은 것입니다.
