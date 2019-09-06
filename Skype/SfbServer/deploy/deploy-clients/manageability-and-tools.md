---
title: Skype 실 시스템 관리 효율성 및 도구
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Skype 대화방 시스템용 관리 도구에 대해 자세히 알아보려면이 항목을 참조 하세요.
ms.openlocfilehash: 51cb9ed85558a97b4afbeed8e4addd2ade6debec
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775329"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 실 시스템 관리 효율성 및 도구
 
Skype 대화방 시스템용 관리 도구에 대해 자세히 알아보려면이 항목을 참조 하세요.
  
## <a name="administrative-portal"></a>관리 포털

비즈니스용 Skype Server 온-프레미스 배포의 경우 Skype 대화방 시스템 관리 포털을 사용 하 여 조직 내에서 Skype 채팅방 시스템 배포를 적극적으로 관리 하 고 모니터링할 수 있습니다.
  
자세한 내용은 다음 문서를 참조 하세요.
  
- [비즈니스용 Skype 서버에서 SRS v1 관리 웹 포털 배포](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Skype 채팅방 시스템 [관리 팩](https://www.microsoft.com/download/details.aspx?id=42320) 을 다운로드 하 고 scom server에 설치 하 여 시스템 센터 운영 관리자 (scom)를 통해이를 모니터링할 수 있습니다. SCOM를 사용 하 여 알림을 설정 하 고, Skype 대화방 시스템의 상태를 모니터링 하 고, 가동 시간 보고서를 생성할 수 있습니다. Skype 채팅방 시스템에는 SCOM server를 가리키도록 구성할 수 있는 사전 설치 된 모니터링 에이전트가 제공 됩니다. Skype 대화방 시스템에서 모니터링 에이전트를 구성 하는 방법을 알아보려면 Skype 채팅방 시스템 제조업체에서 제공 하는 설치 가이드를 참조 하세요.
  
## <a name="exchange-checklist"></a>Exchange 검사 목록

- 자동 검색을 설정 하 고 내부 DNS A/CNAME 레코드를 autodiscover.domain.com에 사용할 수 있는지 확인 합니다.
    
- Ping 자동 검색 (예: Ping Autodiscover.contoso.com).
    
- Microsoft 연결 분석기 도구를 사용 하 여 자동 검색 서비스를 테스트 합니다. 첫 번째 테스트 인 "Office Outlook을 사용 하 여 로그온 할 수 없음"을 선택 합니다.
    
- 회의실에 이미 리소스 사서함이 있는 경우 Skype 대화방 시스템 (페이지 하단에 있는 예제 스크립트)에 대해이 계정을 확장 합니다.
    
## <a name="skype-for-business-checklist"></a>비즈니스용 Skype 검사 목록

- 다음 도구를 실행 합니다.
    
  - 비즈니스용 Skype 모범 사례 분석기     
  - 비즈니스용 Skype 상태 분석 도구 (Excel)    
  - 비즈니스용 Skype 연결 분석기 32 비트 또는 64 비트
    
- [Office 365에 대 한 유용한 새로운 문제 해결 및 분석 도구](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)를 검토 합니다. 비즈니스용 Skype 풀 및 Office Web Apps 서버가 있는지 확인 하 고 비즈니스용 Skype 클라이언트를 사용 하 여 PowerPoint 데크를 공유할 수 있습니다.
    
- 회의실에 이미 리소스 사서함이 있는 경우 비즈니스용 Skype에 대해이 기능을 사용 하도록 설정 합니다.
    
- 필요한 경우 회의실 시스템에 대 한 번호 (전화 번호)를 요청 하 고 Active Directory 도구에서 일반 전화 필드를 업데이트 합니다.
    
## <a name="network"></a>사설망

- Skype 채팅방 시스템에 대 한 유선 네트워크 연결을 사용 하 고 있는지 확인 합니다.
    
- 비즈니스용 Skype에 대 한 네트워크 계획 가이드를 읽어 보세요.
    
- 비즈니스용 Skype 파트너 로부터 비즈니스용 Skype 네트워크 평가를 요청 하세요.
    
- 비즈니스용 Skype 상태 분석 도구 (Excel)에서 캡처한 성능 데이터를 읽어 보세요.
    
- 네트워크 분석 도구를 실행 합니다.
    
- 사전 호출 진단 도구를 실행 합니다.
    
## <a name="skype-room-system-security"></a>Skype 실 시스템 보안

Skype 실 시스템은 비즈니스용 Skype 보안 모델, 권한 관리, SCOM 등의 관리 도구를 사용 하 여 Windows 배포에 완벽 하 게 통합할 수 있는 임베디드 시스템입니다. 기능에는 다음이 포함 됩니다.
  
- 사용자 모드에서 디스크 쓰기를 방지 하는 쓰기 필터 
    
- 앱 락커를 통해 권한이 없는 앱이 실행 되지 않도록 합니다. 사용자 모드에서 모든 USB 포트를 사용할 수 없습니다.
    
  - Skype 채팅방 시스템 하드웨어에는 표준 앱 또는 뷰어가 없습니다. 모든 콘텐츠는 HTTP 또는 RDP 프로토콜을 통해 렌더링 됩니다.
    
  - 기기 PC는 Windows Embedded 표준 7 운영 체제를 실행 합니다. 장치를 포함 하 여 모든 하드웨어는 OEM 파트너가 제공 합니다.
    
  - AD DS (Active Directory 도메인 서비스)에 대 한 선택적 도메인 가입으로 로컬 보안 계정 관리 및 제어권을 사용할 수 있습니다.
    
- 비즈니스용 Skype 관리 센터를 사용 하 여 로컬 관리자 계정을 관리할 수도 있습니다.
    
- Skype 채팅방 시스템은 표준 Microsoft 업데이트 프로세스를 통해 업데이트 됩니다.
    
- Skype 채팅방 시스템은 비즈니스용 Skype로 연결 됩니다.
    
  - 비즈니스용 Skype는 모든 통신 모드에 대 한 종단 간 암호화 및 권한 부여를 사용 합니다.
    
  - Skype 실 시스템은 비즈니스용 Skype 보안 및 규정 준수 표준을 지원 합니다. 자세한 내용은 비즈니스용 [Skype 서버의 보안 계획](../../plan-your-deployment/security/security.md) 을 참조 하세요.
    
## <a name="license"></a>동의

소프트웨어를 정품 인증 하기 위해 KMS를 사용 하 고 있는지 확인 합니다. 그렇다면 비즈니스용 Skype 클라이언트 KMS 키를 확인 하거나 추가 해야 할 수 있습니다. KMS를 사용 하지 않는 경우 비즈니스용 Skype 클라이언트 MAK에 대 한 볼륨 라이선스 키를 요청 합니다.
  
## <a name="license-keys"></a>라이선스 키

Skype 채팅방 시스템은 백그라운드에서 비즈니스용 Skype 데스크톱 클라이언트를 실행 합니다. Skype 채팅방 시스템은 도메인 구성원 인 경우, KMS를 검색 하 게 됩니다. (볼륨 라이선스 KMS 키가 있는 경우 자동으로 활성화 됩니다.) 또한 볼륨 라이선스는 xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx를 표시 하면서 입력 하는 MAK를 제공 합니다. (KMS가 아닌 MAK를 사용 하 여 정품 인증을 받으려면 인터넷에 액세스 해야 합니다.) 자세한 내용은 Office 2013의 볼륨 정품 인증을 참조 하세요.
  
- MAK 키를 입력 하려면 OEM 설정 \> SRS 라이선스 도구로 이동 합니다. 상태 확인을 클릭 합니다. 상태가 "제품이 활성화 되지 않음" 이라고 표시 되 면 키를 입력 합니다.
    
- 정품 인증 하는 동안 "" 소프트웨어 라이선스 서비스에서 제품 키가 유효 하지 않다고 보고 했습니다. "라는 오류가 표시 되는 경우 다음을 확인 합니다.
    
  - 키를 올바르게 입력 했습니다.
    
  - 다른 키가 아닌 비즈니스용 Skype MAK 키를 입력 하셨습니다.
    
  - 시스템에서 인터넷에 접속 합니다.
    
- 전화기를 통해 정품 인증을 받을 수 있지만 먼저 SRS 라이선스 도구를 사용 하 여 정품 인증을 시도 해야 합니다. 전화기를 통해 정품 인증을 받으려면 테스트 모임이 아닌 것으로 테스트 통화가 시작 되지 않는 것입니다. Office 인증 마법사에서 전화 정품 인증을 선택 하 고, Microsoft에 전화를 걸어, 긴 숫자를 입력 하 고, 응답을 입력 합니다.
    
## <a name="certificate-authority"></a>인증 기관

Office Web Apps 서버 2013 인증서에 발급 하는 데 사용 되는 인증 기관 확인 인증서 해지 목록 속성에 HTTP 경로가 포함 되어 있습니다.
  
비즈니스용 Skype 서버를 사용 하는 경우 인증서 파일 (.crt)을 Skype 대화방 시스템으로 가져옵니다. CA 서버의 CertEnroll 공유 또는 도메인에 연결 된 PC의 신뢰할 수 있는 루트 폴더에서 쉽게 얻을 수 있습니다.
  
## <a name="certificates"></a>인증

인증 기관에 인증서 해지 목록에 대 한 http 경로가 있는지 확인 합니다. 그렇지 않은 경우 CA를 포함 하도록 업데이트 합니다.
  
시스템 설정 \> 인증서 관리자에서 Skype 대화방 시스템의 관리자 설정에 인증서를 설치 합니다. 내부 인증서에 대 한 엔터프라이즈 루트 CA가 필요 합니다.
  
필요한 인증서를 획득 하는 한 가지 방법은 인증서를 발급 한 CA를 검색 하는 것입니다. 비즈니스용 skype Server의 경우 비즈니스용 Skype의 PC에서 설정 \> 도구 \> 전화 접속 회의 설정을 클릭 합니다. 이렇게 하면 내부 인증서를 발급 한 CA에서 보호 하는 웹 페이지가 열립니다. 브라우저 주소 표시줄에서 잠금 아이콘을 클릭 하 여 보안 보고서를 표시 합니다. 인증서 보기를 클릭 하 고 CRL 배포 지점의 속성을 확인 합니다. 두 번째 CN 매개 변수는 CA의 서버 이름 이어야 합니다. 이제 해당 주소 \\ \< 에 대 한 Windows 탐색기를 엽니다 \>. CA 서버 이름 \CertEnroll. 두 개의 crl 파일과 .crt 파일을 플래시 드라이브에 복사 하 고 스마트 보드의 왼쪽에 놓습니다.
  
해당 .crt 파일을 신뢰할 수 있는 룸 인증 기관 폴더 아래의 Skype 채팅방 시스템으로 가져옵니다.
  
중개 인증 기관 폴더 아래에 있는 Skype 대화방 시스템에서. s e s 파일을 가져옵니다. (파일을 보려면 인증서 관리자의 파일 확장명 필터를. crl로 변경 해야 합니다.)
  
참고: Office Web Apps 2013 서버는 비즈니스용 Skype와 같은 CA를 공유할 수 있습니다. 모임에서 PowerPoint를 공유 하지 못하는 경우 이를 확인 하 고 위에 설명 된 대로 CA 네트워크 공유 CertEnroll에서 CRT 및 CRL 파일을 가져옵니다. 
  
도메인 구성원 자격은 Skype 채팅방 시스템을 Windows 시스템으로 취급할 수 있고 일부 인증서 측면에 대해 Active Directory를 사용할 수 있기 때문에 일부 작업을 단순화할 수 있습니다. 그러나이를 수동으로 관리 하는 것이 가장 좋습니다.
  

