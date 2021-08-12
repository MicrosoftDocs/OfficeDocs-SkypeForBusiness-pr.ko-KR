---
title: 사용자 계정 관리 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 이 문서의 섹션에서는 Active Directory 사용자 사용, 일시적 사용 안 하도록 설정 또는 제거 하는 방법을 설명 하는 비즈니스용 Skype 서버.
ms.openlocfilehash: 43b48daf7a3ad7242076c29a1372e608130763e8e7add95ac86e97ed9c3a9e97
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850183"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>사용자 계정 관리 비즈니스용 Skype 서버

이 문서의 섹션에서는 Active Directory 사용자 사용, 일시적 사용 안 하도록 설정 또는 제거 하는 방법을 설명 하는 비즈니스용 Skype 서버.

Active Directory 사용자를 사용하도록 설정하는 방법에 대한 자세한 내용은 [Create a New User Account를 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)) Active Directory 사용자를 삭제하는 방법에 대한 자세한 내용은 [Delete a User Account를 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

이러한 절차는 사용률이 가장 낮은 경우 유지 관리 기간 비즈니스용 Skype 수행해야 합니다. 이 수행 여부는 조직의 요구에 따라 결정됩니다.

이 문서에는 다음 절차가 포함되어 있습니다.

- [한 명 이상의 사용자를 검색하려면](user-accounts.md#Search)

- [새 사용자 추가 및 비즈니스용 Skype 서버 사용](user-accounts.md#Add)

- [이전에 사용자 계정에서 사용하도록 설정한 사용자 계정을 사용하지 않도록 설정하거나 다시 비즈니스용 Skype 서버](user-accounts.md#Disable)

- [사용자를 사용하지 않도록 Enterprise Voice](user-accounts.md#Disable_EV)

- [관리 셸을 사용하여 사용자 비즈니스용 Skype 서버 제거](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>한 명 이상의 사용자를 검색하려면
<a name="Search"> </a>

검색 쿼리의 결과를 사용하여 검색 쿼리에 대해 Active Directory 사용자를 구성할 수 비즈니스용 Skype 서버. 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다.

비즈니스용 Skype 서버 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수 있습니다. 다음 절차에서는 제어판을 사용하여 사용자를 비즈니스용 Skype 서버 방법을 설명합니다.

> [!NOTE]
> 중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소로 사용자를 검색할 때 검색 결과가 정확하지 않을 수 있습니다. 이러한 경우에는 sip:name과 같은 SIP 주소 접두사를 지정하여 사용자를 검색하거나, 검색 필터를 추가하고 전자 메일 주소의 일부분이 포함된 SIP 주소를 선택하거나, **Get-CSUser** cmdlet을 사용할 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 검색할 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI를 모두 입력하거나 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.

   a. 화면 오른쪽 위의 **검색 결과** 위에 있는 확장 화살표 단추를 클릭하고 **필터 추가** 를 클릭합니다.

   b. 사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.

   c. **같음** 목록에서 **같음** 또는 **같지 않음** 을 클릭합니다.

   d. 텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 **찾기** 를 입력합니다.

6. **검색 결과** 아래에 검색 결과가 나타납니다. 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>새 사용자 추가 및 비즈니스용 Skype 서버 사용
<a name="Add"> </a>

Active Directory 사용자 및 컴퓨터에서 사용자 계정을 사용하도록 설정한 후 비즈니스용 Skype 서버 제어판을 사용하여 Active Directory 사용자를 추가하여 새 비즈니스용 Skype 서버 사용자 계정을 만들고 사용하도록 설정할 수 비즈니스용 Skype 서버.

특히 [Enable-CsUser](/powershell/module/skype/enable-csuser)cmdlet을 사용할 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 사용** 을 클릭합니다.

5. **새 Lync Server 사용자** 대화 상자에서 **추가** 를 클릭합니다.

6. **사용자 검색** 상자에 원하는 Active Directory 사용자 계정의 이름, 표시 이름, 성, SAM(보안 계정 관리자) 계정 이름, 전자 메일 주소, UPN(사용자 계정 이름) 또는 전화 번호를 모두 또는 일부분 입력하고 **찾기** 를 클릭합니다.

7. 표에서 추가하려는 계정을 비즈니스용 Skype 서버 확인을 **클릭합니다.**

8. 풀에 사용자를 할당하고, 세부 정보를 추가로 지정하고, 원하는 사용자에게 정책을 할당한 후에 **사용** 을 클릭합니다.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>이전에 사용자 계정에서 사용하도록 설정한 사용자 계정을 사용하지 않도록 설정하거나 다시 비즈니스용 Skype 서버
<a name="Disable"> </a>

다음 절차에 따라 사용자 계정에 대해 구성한 비즈니스용 Skype 서버 설정은 잃지 않고 이전에 사용하도록 설정된 사용자 계정을 비즈니스용 Skype 서버 수 있습니다. 사용자 계정 비즈니스용 Skype 서버 손실되지 않으면서 사용자 계정을 다시 구성하지 않고 이전에 사용하도록 설정한 사용자 계정을 다시 사용하도록 설정할 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 클릭합니다.

6. **동작** 메뉴에서 다음 중 하나를 수행합니다.

   - Lync Server의 사용자 계정을 비즈니스용 Skype 서버 일시적으로 사용하지 않도록 **설정하려면 Lync Server 에** 대해 일시적으로 사용하지 않도록 설정을 클릭합니다.

   - 사용자 계정을 사용하도록 설정하려면 비즈니스용 Skype 서버 **Lync Server에** 대해 다시 사용하도록 설정을 클릭합니다.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Powershell Windows 사용하여 사용자 계정 사용 안 하도록 설정 또는 다시 사용

**Set-CsUser** cmdlet을 사용하여 사용자 계정을 일시적으로 사용하지 않도록 설정한 다음 나중에 다시 사용하도록 설정할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 서버를 사용하여 Windows PowerShell 연결하는 비즈니스용 Skype 서버 ["빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)블로그 문서를 참조하십시오. 프로세스는 동일한 비즈니스용 Skype 서버.

### <a name="to-disable-a-user-account"></a>사용자 계정을 사용하지 않도록 설정하려면

- 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 Enabled 속성의 값을 False($False)로 설정합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>사용자 계정을 다시 사용하도록 설정하려면

- 사용하지 않도록 설정된 사용자 계정을 다시 사용하도록 설정하려면 Enabled 속성의 값을 True($True)로 설정합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

자세한 내용은 [Set-CsUser](/powershell/module/skype/set-csuser) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="disable-a-user-for-enterprise-voice"></a>사용자를 사용하지 않도록 Enterprise Voice
<a name="Disable_EV"> </a>

다음 절차에 따라 Enterprise Voice 사용하도록 설정된 사용자 계정에 대해 이 설정을 사용하지 않도록 비즈니스용 Skype 서버.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>사용자 계정을 사용하지 않도록 설정하려면 Enterprise Voice

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.

6. **편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.

7. **Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice** 를 제외한 아무 옵션이나 클릭합니다.

    > [!NOTE]
    > 사용자가 Lync를 사용하여 오디오 또는 화상 통화를 하지 않도록 제한하려면 전화 통신에서 오디오/비디오 사용 안 **를 클릭합니다.**

8. **커밋** 을 클릭합니다.

이제 사용자가 Enterprise Voice 없습니다. 관련 정보: <br/>[Enterprise Voice 및 모바일](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [사용자가 Enterprise Voice 사용하도록 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [비즈니스용 Skype 서버 관리 쉘](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 사용자 비즈니스용 Skype 서버 제거
<a name="Remove"> </a>

다음 절차에 따라 이전에 추가한 사용자 계정을 제거할 수 비즈니스용 Skype 서버.

> [!NOTE]
> 사용자를 제거하면 사용자 계정에 대해 구성한 모든 설정이 손실됩니다. 대신 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 이전에 사용자 계정 사용 안 하도록 설정하거나 다시 사용하도록 설정 을 [비즈니스용 Skype 서버.](user-accounts.md#Disable)

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 제거할 사용자 계정을 클릭합니다.

6. **동작** 메뉴에서 **Lync Server에서 제거** 를 선택하면 대화 상자가 나타납니다.

7. 대화 상자에서 **확인** 을 선택하여 사용자를 제거합니다.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Powershell cmdlet을 Windows 사용자 계정 제거

이 cmdlet을 사용하여 사용자 계정을 제거할 Disable-CsUser 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 실행할 수 Windows PowerShell. 원격 서버를 사용하여 Windows PowerShell 연결하는 비즈니스용 Skype 서버 ["빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)블로그 문서를 참조하십시오. 프로세스는 동일한 비즈니스용 Skype 서버.

### <a name="to-remove-a-user-account"></a>사용자 계정을 제거하려면
사용자 계정을 제거하려면 Disable-CsUser cmdlet을 사용합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

이 명령을 실행한 후에는 계정 및 이전 설정을 다시 사용하도록 설정할 수 없습니다. 대신 Enable-CsUser cmdlet을 사용하여 Ken Myer에 대해 새 계정을 만들어야 합니다.

자세한 내용은 [Disable-CsUser](/powershell/module/skype/disable-csuser) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="see-also"></a>참고 항목
<a name="Remove"> </a>

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csusers)
