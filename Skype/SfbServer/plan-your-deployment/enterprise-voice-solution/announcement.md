---
title: 2016년 8월의 공지 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 조직에서 비즈니스용 Skype 서버 Enterprise Voice 전화 번호로 전화를 걸 때 할 작업을 구성하는 2013의 공지 응용 프로그램 계획 오디오 파일 요구 사항을 포함합니다.
ms.openlocfilehash: 010e49a8578a6ec2482b454b2fb62ca8718939d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583912"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>2016년 8월의 공지 비즈니스용 Skype

조직에서 비즈니스용 Skype 서버 Enterprise Voice 전화 번호로 전화를 걸 때 할 작업을 구성하는 2013의 공지 응용 프로그램 계획 오디오 파일 요구 사항을 포함합니다.

비즈니스용 Skype 서버 알림 응용 프로그램을 사용하면 전화 걸기 번호가 조직에 유효하지만 사용자나 전화에 할당되지 않은 경우 수신 전화 통화 처리를 구성할 수 있습니다. 이러한 통화를 미리 정해진 대상(전화 번호, SIP URI 또는 음성 메일)으로 전송하거나 오디오 공지를 재생하거나 둘 다를 재생할 수 있습니다. 공지사항 응용 프로그램을 사용하면 발신자 통화 중 신호음이 들리거나 SIP 클라이언트에서 오류 메시지가 수신되는 상황을 방지할 수 있습니다. 이 섹션에는 공지 응용 프로그램과 관련한 계획 정보가 포함되어 있습니다.

공지사항 응용 프로그램을 배포할 때 다른 사람이 미지정 번호로 전화를 걸 때 수행되는 작업을 결정하는 미지정 번호 테이블을 구성해야 합니다. 지정되지 않은 번호 테이블에는 조직에 유효한 전화 번호 범위가 포함되어 있으며 각 범위를 처리하는 공지사항 응용 프로그램을 지정합니다. 발신자가 조직에 유효하지만 누구에게도 할당되지 않은 전화 번호로 전화를 걸면 비즈니스용 Skype 서버 지정되지 않은 번호 라우팅 테이블에서 번호를 하여 번호가 들어 있는 범위를 식별하고 해당 범위에 지정된 공지사항 응용 프로그램으로 통화를 라우팅합니다. 공지 응용 프로그램은 통화에 응답하고 오디오 메시지를 재생한 다음(이렇게 구성한 경우) 통화 연결을 끊거나 통신사와 같이 미리 정해진 대상으로 통화를 전송합니다. 관리 셸 cmdlet을 비즈니스용 Skype 서버 여러 오디오 메시지를 구성하거나 대상을 전송할 수 있습니다.

지정되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 더 이상 사용되지 않는 특정 번호가 있는 경우 각 번호별로 지정된 메시지를 재생하려면 지정되지 않은 번호 테이블에 해당 특정 번호를 입력하면 됩니다. 예를 들어 고객 서비스 센터의 번호를 변경한 경우 이전 고객 서비스 번호를 입력하고 새 번호를 제공하는 알림과 연결할 수 있습니다. 지정되지 않은 번호(예: 퇴사한 직원의 번호)로 전화를 건 모든 사람에게 일반 메시지를 재생하려면 조직의 유효한 모든 내선 번호 범위를 입력하면 됩니다. 그러면 발신자가 현재 지정되지 않은 번호로 전화를 걸 때마다 지정되지 않은 번호 테이블이 호출됩니다.

## <a name="deployment-and-requirements"></a>배포 및 요구 사항

Tthe Announcement 응용 프로그램은 응답 그룹 응용 프로그램과 함께 자동으로 설치됩니다. 공지 사항 및 응답 그룹 응용 프로그램은 Enterprise Voice 배포의 표준 구성 요소입니다. Enterprise Voice 두 응용 프로그램은 모두 자동으로 배포됩니다.

### <a name="software-requirements"></a>소프트웨어 요구 사항

공지 사항을 실행하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에는 Windows Server 2008 R2를 실행하는 서버에 대해 Windows 미디어 형식 런타임이 설치되어 있어야 합니다. 또는 R2를 실행하는 서버의 경우 Microsoft Media Foundation이 Windows Server 2012 Windows Server 2012 있어야 합니다. Windows Server 2008 R2의 경우 Windows 데스크톱 환경의 일부로 Windows 미디어 형식 런타임이 설치됩니다. Windows 공지사항 및 음악에 대해 재생되는 Windows 미디어 오디오(.wma) 파일에는 미디어 형식 런타임 또는 Microsoft 미디어 파운데이션이 필요합니다.

### <a name="port-requirements"></a>포트 요구 사항

공지 응용 프로그램은 SIP **수신 요청에 포트 5071을** 사용 합니다.

> [!NOTE]
> 이 포트는 기본 설정이며 **Set-CsApplicationServer** cmdlet을 사용하여 변경할 수 있습니다. 이 cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

### <a name="audio-file-requirements"></a>오디오 파일 요구 사항

공지사항 응용 프로그램은 음악 및 Windows 미디어 오디오(.wma) 파일 형식과 웨이브(.wav) 파일 형식을 지원합니다. 공지 사항 응용 프로그램의 오디오 파일 요구 사항은 응답 그룹 응용 프로그램과 동일합니다. 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.