---
title: 비즈니스용 Skype의 공지 프로그램 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 조직의 미지정 전화 번호에 대한 전화 통화를 Enterprise Voice 구성하는 비즈니스용 Skype 서버 2013의 공지 응용 프로그램 계획 오디오 파일 요구 사항을 포함합니다.
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813758"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>비즈니스용 Skype의 공지 프로그램 계획

조직의 미지정 전화 번호에 대한 전화 통화로 할 작업을 구성하는 비즈니스용 Skype Enterprise Voice 서버에서 공지 응용 프로그램을 계획합니다. 오디오 파일 요구 사항을 포함합니다.

비즈니스용 Skype 서버 알림 응용 프로그램을 사용하면 전화 걸기 번호가 조직에 유효하지만 사용자나 전화에 할당되지 않은 경우 수신 전화 통화 처리를 구성할 수 있습니다. 이러한 통화를 미리 정해진 대상(전화 번호, SIP URI 또는 음성 메일)으로 전송하거나 오디오 공지 사항을 재생하거나 둘 다를 재생할 수 있습니다. 공지 응용 프로그램을 사용하면 발신자 통화 중 전화를 걸거나 통화 중 신호음이 들리거나 SIP 클라이언트에서 오류 메시지가 수신되는 상황을 방지할 수 있습니다. 이 섹션에는 공지 프로그램과 관련한 계획 정보가 포함되어 있습니다.

공지 응용 프로그램을 배포할 때 다른 사람이 미지정 번호로 전화를 걸 때 수행되는 작업을 결정하는 미지정 번호 테이블을 구성해야 합니다. 지정되지 않은 번호 테이블에는 조직에 유효한 전화 번호 범위가 포함되어 있으며 각 범위를 처리하는 공지사항 응용 프로그램을 지정합니다. 발신자가 조직에 유효하지만 누구에게도 할당되지 않은 전화 번호로 전화를 걸면 비즈니스용 Skype 서버는 지정되지 않은 번호 라우팅 테이블에서 번호를 검색하고 번호가 들어 있는 범위를 식별하고 해당 범위에 지정된 공지사항 응용 프로그램으로 통화를 라우팅합니다. 공지 응용 프로그램은 통화에 응답하고 오디오 메시지를 재생한 다음(이렇게 구성한 경우) 통화 연결을 끊거나 운영자 등의 미리 정해진 대상으로 통화를 전송합니다. 비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 여러 오디오 메시지를 구성하거나 대상을 전송할 수 있습니다.

지정되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 더 이상 사용되지 않는 특정 번호가 있는 경우 각 번호별로 지정된 메시지를 재생하려면 지정되지 않은 번호 테이블에 해당 특정 번호를 입력하면 됩니다. 예를 들어 고객 서비스 센터의 번호를 변경한 경우 이전 고객 서비스 번호를 입력하고 새 번호를 제공하는 알림과 연결할 수 있습니다. 지정되지 않은 번호(예: 퇴사한 직원의 번호)로 전화를 건 모든 사람에게 일반 메시지를 재생하려면 조직의 유효한 모든 내선 번호 범위를 입력하면 됩니다. 그러면 발신자가 현재 지정되지 않은 번호로 전화를 걸 때마다 지정되지 않은 번호 테이블이 호출됩니다.

## <a name="deployment-and-requirements"></a>배포 및 요구 사항

Tthe Announcement 응용 프로그램은 응답 그룹 응용 프로그램과 함께 자동으로 설치됩니다. 공지 사항 및 응답 그룹 응용 프로그램은 Enterprise Voice 구성 요소입니다. 이 두 응용 Enterprise Voice 모두 자동으로 배포됩니다.

### <a name="software-requirements"></a>소프트웨어 요구 사항

공지 응용 프로그램을 실행하는 모든 프런트 엔드 서버 또는 Standard Edition Server에는 Windows Server 2008 R2를 실행하는 서버에 대해 Windows Media 형식 런타임이 설치되어 있어야 합니다. 또는 Microsoft Media Foundation for servers for Windows Server 2012 또는 Windows Server 2012 R2를 실행해야 합니다. Windows Server 2008 R2의 경우 Windows Media 형식 런타임은 Windows 데스크톱 환경의 일부로 설치됩니다. 공지사항 및 음악에 대해 발표 응용 프로그램이 재생하는 Windows Media 오디오(.wma) 파일에는 Windows Media 형식 런타임 또는 Microsoft Media Foundation이 필요합니다.

### <a name="port-requirements"></a>포트 요구 사항

공지 응용 프로그램은 SIP **수신 요청에 포트 5071을** 사용 합니다.

> [!NOTE]
> 이 포트는 기본 설정이며 **Set-CsApplicationServer** cmdlet을 사용하여 변경할 수 있습니다. 이 cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

### <a name="audio-file-requirements"></a>오디오 파일 요구 사항

공지 응용 프로그램은 음악 및 공지 사항을 위해 웨이브(.wav) 파일 형식 및 Windows Media 오디오(.wma) 파일 형식을 지원합니다. 공지 사항 응용 프로그램에 대한 오디오 파일 요구 사항은 응답 그룹 응용 프로그램과 동일합니다. 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.


