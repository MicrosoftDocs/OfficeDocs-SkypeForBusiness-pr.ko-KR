---
title: 제어판-업데이트 된 사용자 검색
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: 검색 쿼리의 결과를 사용 하 여 비즈니스용 Skype 서버용 사용자를 구성할 수 있습니다. 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 URI (Uniform Resource Identifier)를 기준으로 사용자를 검색할 수 있습니다. Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용 하 여 사용자를 검색할 수도 있습니다.
ms.openlocfilehash: 1076b4e5d316a76c57f106179f7c6736ddcb8761
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704123"
---
# <a name="control-panel---updated-user-search"></a>사용자 검색

검색 쿼리의 결과를 사용 하 여 비즈니스용 Skype 서버용 사용자를 구성할 수 있습니다. 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 URI (Uniform Resource Identifier)를 기준으로 사용자를 검색할 수 있습니다. Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용 하 여 사용자를 검색할 수도 있습니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**사용자 검색** 제어판 페이지에서 다음 작업을 수행할 수 있습니다.

- [사용자 검색](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [사용자 사용 또는 사용 안 함](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [사용자 이동](ms.lync.lscp.UserMove.md)

- [모든 사용자 이동](ms.lync.lscp.UserMoveAll.md)

- [사용자에 게 정책 할당](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [사용자에 대 한 페더레이션, 원격 사용자 액세스 및 공용 IM 연결 구성](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [사용자를 위한 전화 접속 구성](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>UI 참조

다음 목록에서는 **사용자 검색** 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명 합니다.

### <a name="user-search"></a>사용자 검색

- **검색** 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 회선 URI의 첫 번째 부분을 사용 하 여 사용자를 검색 합니다.

- **LDAP 검색** LDAP 식을 입력 하 여 사용자를 검색 합니다.

- **사용자 검색 상자** 검색 하려는 사용자 데이터 또는 LDAP 식을 입력 합니다.

- **찾기** **사용자 검색** 및 상자에 입력 한 검색 값과 일치 하는 사용자를 표시 하려면 클릭 합니다.

- **쿼리 열기** 저장 된 검색 쿼리를 클릭 하 여 엽니다.

- **쿼리 저장** 검색 쿼리를 저장 하려면 클릭 합니다.

- **+ 필터 추가** 를 클릭 하 여 추가 검색 조건을 추가 합니다.

- **검색 필터 필드** 검색 결과를 필터링 할 필드를 선택 하 고 쿼리의 연산자를 선택한 다음 검색 하려는 문자열을 입력 합니다.

- **표시할 최대 사용자 수** 표시할 검색 결과의 수를 입력 하거나 위쪽 및 아래 화살표 키를 사용 하 여 숫자를 지정 합니다.

적절 하 게 다른 설명 텍스트를 추가 합니다.

### <a name="search-results-menus"></a>검색 결과 메뉴

- **사용자 설정** 비즈니스용 Skype 서버에 새 사용자를 추가할 수 있는 [사용자: 새 Lync Server 사용자](ms.lync.lscp.UserNew.md) 대화 상자를 클릭 하 여 엽니다.

    새 연락처를 추가 하려면 아래쪽 화살표를 클릭 한 다음 **대화 가능** 을 선택 하 여 [사용자: 새 연락처 개체](ms.lync.lscp.UserNewContact.md) 대화 상자를 엽니다.

- **편집** **편집** 을 클릭 한 다음 **세부 정보 표시** 를 클릭 하 여 선택한 사용자의 세부 정보를 표시 하거나 **모든 검색 결과 선택을** 클릭 하 여 결과 테이블에 표시 된 모든 사용자를 선택 합니다.

- **작업** **작업**을 클릭 한 다음 검색 결과에서 선택한 사용자에 대해 수행할 작업을 선택 합니다. 사용할 수 있는 작업은 다음과 같습니다.

  - **Lync Server에 대해 다시 사용 하도록 설정** 선택한 사용자 계정이 일시적으로 사용 하지 않도록 설정 된 후 사용 하도록 설정 합니다.

  - **Lync Server에서 일시적으로 사용 하지 않도록 설정** 사용자 계정을 제거 하지 않고 다시 사용 하도록 설정할 때까지 비즈니스용 Skype 서버에서 사용자 계정을 사용 하지 않도록 설정 합니다.

  - **정책 할당** 사용자에 게 할당 된 정책을 구성할 수 있는 [사용자: 정책 할당](ms.lync.lscp.UserAssignPolicy.md) 대화 상자를 엽니다.

  - **핀 상태 보기** 선택한 사용자의 PIN 데이터를 표시 하는 [사용자: 핀 상태 보기](ms.lync.lscp.UserViewPin.md) 대화 상자를 엽니다.

  - **PIN 설정** 선택한 사용자의 PIN을 설정할 수 있는 [Pin 설정](ms.lync.lscp.UserSetPin.md) 대화 상자를 엽니다.

  - **고정 핀** 사용자의 PIN을 잠급니다.

  - **PIN 잠금 해제** 사용자의 PIN에 대 한 잠금을 제거 합니다.

  - **Lync Server에서 제거** 비즈니스용 Skype 서버에서 사용자 계정을 제거 합니다. 사용자가 Active Directory에서 제거 되지 않았습니다.

  - **사용자 인증서 제거** 사용자에 게 부여 된 모든 인증서를 제거 합니다.

  - **선택한 사용자를 풀로 이동** 선택한 사용자를 이동할 풀을 선택할 수 있는 [사용자 이동](ms.lync.lscp.UserMove.md) 대화 상자를 엽니다.

  - **모든 사용자를 풀로 이동** 그룹을 선택 하 여 선택한 모든 사용자를 이동할 수 있는 [사용자 이동](ms.lync.lscp.UserMove.md) 대화 상자를 엽니다.


