---
title: 제어판 - 업데이트된 사용자 검색
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 검색 쿼리의 결과를 사용하여 검색 쿼리에 대해 사용자를 구성할 수 비즈니스용 Skype 서버. 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다. Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수도 있습니다.
ms.openlocfilehash: 8ebb4c7d1c8288d3dfaef689422396130490aca0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849041"
---
# <a name="control-panel---updated-user-search"></a>제어판-업데이트 됨: 사용자 검색

검색 쿼리의 결과를 사용하여 검색 쿼리에 대해 사용자를 구성할 수 비즈니스용 Skype 서버. 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다. Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수도 있습니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

사용자 검색 제어판 페이지에서는 다음 **작업을** 수행할 수 있습니다.

- [Lync Server 2010 사용자 검색](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Lync Server 2010에 대해 사용자 사용 또는 사용 안 하도록 설정](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [사용자 이동](move-user.md)

- [모든 사용자 이동](move-all-users.md)

- [사용자에게 정책 할당](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [사용자가 Enterprise Voice 2015에서 비즈니스용 Skype 서버 사용](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [사용자에 대한 페더전, 원격 사용자 액세스 및 공용 IM 연결 구성](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [사용자에 대한 전화 통신 구성](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 [Manage 비즈니스용 Skype 서버 2015를 참조합니다.](../../manage/manage.md)

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 **사용자 검색** 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

### <a name="user-search"></a>사용자 검색

- **검색** 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI의 첫 부분으로 사용자를 검색합니다.

- **LDAP 검색** LDAP 식을 입력하여 사용자를 검색합니다.

- **사용자 검색 상자** 원하는 사용자 데이터 또는 LDAP 식을 입력합니다.

- **찾기** 사용자 검색 및 상자에 입력한 검색 값과 일치하는 사용자를 클릭하여 표시합니다. 

- **쿼리 열기** 저장된 검색 쿼리를 클릭하여 열 수 있습니다.

- **저장 쿼리** 검색 쿼리를 저장하려면 클릭합니다.

- **+ 필터 추가** 검색 조건을 더 추가하려면 클릭합니다.

- **검색 필터 필드** 검색 결과를 필터링할 필드를 선택하고 쿼리 연산자를 선택한 다음 검색할 문자열을 입력합니다.

- **표시할 최대 사용자 수** 표시할 검색 결과 수를 입력하거나 위쪽 및 아래쪽 화살표를 사용하여 숫자를 지정합니다.

설명 텍스트를 적절하게 더 추가합니다.

### <a name="search-results-menus"></a>검색 결과 메뉴

- **사용자 사용** 새 사용자를 추가할 수 있는 [사용자: 새 Lync Server 사용자](users-new-lync-server-user.md) 대화 상자를 클릭하여 비즈니스용 Skype 서버.

    새 연락처를 추가하려면 아래쪽 화살표를 클릭하고 **연락처 사용** 을 선택하여 [Users: New Contact Objects](users-new-contact-objects.md) 대화 상자를 엽니다.

- **편집** 편집을 클릭한  다음 세부 정보 표시를 클릭하여 선택한 사용자의  세부 정보를 표시하거나 모든 검색 결과 선택을 클릭하여 결과 테이블에 표시된 모든 사용자를 선택합니다. 

- **작업** 작업을 **클릭한** 다음 검색 결과에서 선택한 사용자에 대해 수행할 작업을 선택합니다. 사용할 수 있는 작업은 다음과 같습니다.

  - **Lync Server에 대해 다시 사용하도록 설정** 일시적으로 사용하지 않도록 설정한 후 선택한 사용자 계정을 활성화합니다.

  - **Lync Server에 대해 일시적으로 사용하지 않도록 설정** 사용자 계정을 제거하지 비즈니스용 Skype 서버 다시 사용하도록 설정할 때까지 계정에서 사용자 계정을 사용하지 않도록 설정합니다.

  - **정책 할당** 사용자에게 [할당된 정책을](users-assign-policies.md) 구성할 수 있는 사용자: 정책 할당 대화 상자를 개설합니다.

  - **PIN 상태 보기** 선택한 사용자의 PIN 데이터를 표시하는 [사용자: PIN](users-view-pin-status.md) 상태 보기 대화 상자를 열 수 있습니다.

  - **PIN 설정** 선택한 사용자의 [PIN을](set-pin.md) 설정할 수 있는 PIN 설정 대화 상자가 열립니다.

  - **PIN 잠금** 사용자의 PIN을 잠그습니다.

  - **PIN 잠금 해제** 사용자의 PIN에 대한 잠금을 제거합니다.

  - **Lync Server에서 제거** 사용자 계정을 사용자 계정에서 비즈니스용 Skype 서버. 사용자가 Active Directory에서 제거되지 않습니다.

  - **사용자 인증서 제거** 사용자에게 부여된 모든 인증서를 제거합니다.

  - **선택한 사용자를 풀로 이동** 선택한 [사용자를](move-user.md) 이동할 풀을 선택할 수 있는 사용자 이동 대화 상자가 열립니다.

  - **모든 사용자를 풀로 이동** 선택한 [모든](move-user.md) 사용자를 이동할 풀을 선택할 수 있는 사용자 이동 대화 상자가 열립니다.