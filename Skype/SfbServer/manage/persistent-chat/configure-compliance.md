---
title: 영구 채팅 서버에 대한 준수 서비스 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 준수 서비스를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 54131eeddc95afd71978ada3a84fba3d4ab52716
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817239"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>영구 채팅 서버에 대한 준수 서비스 구성

**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 준수 서비스를 구성 하는 방법에 대해 알아봅니다.

영구 채팅 준수를 통해 관리자는 영구 채팅 메시지 및 활동을 보관할 수 있습니다. 준수 서비스는 참가자가 다음을 비롯 한 각 영구 채팅 서버 대화와 관련 된 데이터를 기록 하 고 보관 합니다.

- 영구 대화방에 참가

- 채팅방을 벗어납니다.

- 메시지를 게시 합니다.

- 채팅 기록 보기

- 파일을 업로드 합니다.

- 파일을 다운로드 합니다.

이 정보는 필요에 따라 준수 SQL 데이터베이스에서 검색할 수 있습니다. 

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 준수 서비스 구성

토폴로지 작성기를 사용 하 여 준수 서비스를 사용 하도록 설정한 후 **CsPersistenChatComplianceConfiguration** cmdlet을 사용 하 여 서비스를 구성할 수 있습니다.

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

또는

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

다음 매개 변수를 설정할 수 있습니다.

- AdapterType-어댑터 유형을 지정할 수 있습니다. 어댑터는 준수 데이터베이스의 데이터를 특정 형식으로 변환 하는 타사 제품입니다. XML이 기본값입니다.

- OneChatRoomPerOutputFile-이 매개 변수를 사용 하면 각 채팅방에 대해 별도의 보고서를 만들도록 지정할 수 있습니다.

- AddChatRoomDetails-이 매개 변수를 사용 하면 데이터베이스의 각 채팅방에 대 한 추가 세부 정보를 기록 합니다. 이 설정은 데이터베이스 크기를 크게 증가 시킬 수 있으므로 기본적으로 비활성화 되어 있습니다.

- AddUserDetails-사용 하는 경우이 매개 변수는 데이터베이스의 각 채팅방 사용자에 대 한 추가 세부 정보를 기록 합니다. 이 설정은 데이터베이스 크기를 크게 증가 시킬 수 있으므로 기본적으로 비활성화 되어 있습니다.

- Id-이 매개 변수는 전역, 사이트 및 서비스 수준을 포함 하 여 규정 준수 설정을 특정 컬렉션에 대해 범위 지정 하도록 허용 합니다. 기본값은 전역 수준입니다. 

- RunInterval-이 매개 변수는 서버가 다음 준수 출력 파일을 만들기 까지의 시간 (기본값은 15 분)을 결정 합니다.

## <a name="use-a-customized-compliance-adapter"></a>사용자 지정 준수 어댑터 사용

영구 채팅 서버와 함께 설치 된 XmlAdapter를 사용 하는 대신 사용자 지정 어댑터를 작성할 수 있습니다. 이를 수행 하려면 **IComplianceAdapter** 인터페이스를 구현 하는 공용 클래스를 포함 하는 .net Framework 어셈블리를 제공 해야 합니다. 이 어셈블리는 영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에 배치 해야 합니다. 규정 준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 규정 준수 서버는 어댑터의 여러 인스턴스에 대 한 중복 준수 데이터를 제공 하지 않습니다.

인터페이스는 네임 스페이스 `Microsoft.Rtc.Internal.Chat.Server.Compliance`의 준수 .dll 어셈블리에 정의 되어 있습니다. 인터페이스는 사용자 지정 어댑터에서 구현 해야 하는 두 가지 메서드를 정의 합니다.

영구 채팅 준수 서버는 어댑터가 처음 로드 될 때 다음 메서드를 호출 하 게 됩니다. 에 `AdapterConfig` 는 준수 어댑터와 관련 된 지속적인 채팅 준수 구성이 포함 되어 있습니다.

```cpp
void SetConfig(AdapterConfig config)
```

영구 채팅 준수 서버는 변환할 새 데이터가 있는 경우 정기적으로 다음 메서드를 호출 합니다. 이 시간 간격은 영구 채팅 준수 구성 `RunInterval` 에 설정 된 as와 동일 합니다.

```cpp
void Translate(ConversationCollection conversations)
```

에 `ConversationCollection` 는이 메서드를 마지막으로 호출 했을 때 수집 된 대화 정보가 포함 됩니다.

## <a name="customize-the-xslt-definition-file"></a>XSLT 정의 파일 사용자 지정

준수 데이터는 XML로 제공 되며, XSLT 정의 파일을 사용 하 여 조직에 가장 잘 맞는 형식으로 변환할 수 있습니다. 이 항목에서는 규정 준수 서비스가 만드는 XML 파일에 대해 설명 합니다. 또한 XSLT 정의 및 출력 파일에 대 한 샘플을 제공 합니다.

### <a name="output-format"></a>출력 형식

준수 서비스 출력은 다음 코드 예제에 표시 된 것 처럼 대화 (대화 요소)와 메시지 (메시지 요소) 순으로 분류 됩니다.

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

대화 요소에는 4 개의 요소 (채널, FirstMessage, StartTimeUTC 및 EndTimeUTC)가 포함 됩니다. 채널 요소는 채팅방의 URI (Uniform Resource Identifier)를 포함 하 고 FirstMessage 요소는 Messages 요소의 첫 번째 메시지를 설명 합니다. StartTimeUTC 및 EndTimeUTC 요소는 다음 코드 예제에 표시 된 것 처럼 대화에 대 한 시작 및 종료 시간을 제공 합니다.

```XML
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Message 요소에는 두 개의 요소 (Sender 및 DateTimeUTC)와 세 가지 특성 (유형, 콘텐츠 및 ID)이 포함 되어 있습니다. Sender 요소는 메시지를 보내는 사용자를 나타내고 DateTimeUTC 요소는 다음 코드 예제에 표시 된 대로 이벤트가 발생 하는 시기를 나타냅니다.

```XML
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

다음 표에서는 메시지 특성 유형, 콘텐츠 및 ID에 대해 설명 합니다.

**메시지 요소 특성**

|**특성**|**설명**|**선택/필수**|
|:-----|:-----|:-----|
|유형  <br/> |메시지 유형을 지정 합니다. 메시지 유형은 메시지 요소 메시지 유형 테이블에 설명 되어 있습니다.  <br/> |필수  <br/> |
|콘텐트가  <br/> |메시지의 내용이 포함 됩니다. 조인 또는 파트 유형의 메시지는이 특성을 사용 하지 않습니다.  <br/> |선택  <br/> |
|I  <br/> |콘텐츠의 고유 ID를 지정 합니다. 이 특성은 채팅 유형의 메시지에만 사용 됩니다.  <br/> |선택  <br/> |

각 보낸 사람 요소에는 사용자 이름, ID, 전자 메일, 내부, URI의 다섯 가지 특성이 있습니다. 다음 표에서는 이러한 특성에 대해 설명 합니다.

**보낸 사람 요소 특성**

|**특성**|**설명**|**선택/필수**|
|:-----|:-----|:-----|
|사용자  <br/> |보낸 사람의 이름입니다.  <br/> |선택  <br/> |
|I  <br/> |보낸 사람의 고유 ID입니다.  <br/> |필수  <br/> |
|메일 주소  <br/> |보낸 사람의 전자 메일 주소입니다.  <br/> |선택  <br/> |
|내부용  <br/> |사용자가 내부 사용자 인지 페더레이션 사용자 인지 확인 합니다. 값이 true로 설정 되 면 사용자는 내부용입니다.  <br/> |선택  <br/> |
|Url  <br/> |사용자의 SIP URI입니다.  <br/> |필수  <br/> |

다음 예제에서는 Messages 요소에 포함 될 수 있는 메시지 형식을 보여 줍니다. 또한 각 요소를 사용 하는 방법에 대 한 예제를 제공 합니다.

참가-사용자가 채팅방에 참가 합니다.

```XML
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

파트-사용자가 채팅방을 벗어납니다.

```XML
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

채팅-보낸 사람의 전자 메일 주소입니다.

```XML
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

배경 채팅-사용자가 채팅 기록에서 콘텐츠를 요청 합니다.

```XML
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

파일 업로드-사용자가 파일을 업로드 합니다.

```XML
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

파일 다운로드-사용자가 파일을 다운로드 합니다.

```XML
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>기본 영구 채팅 출력 XSD 및 예제 XSL 변환

다음 코드 샘플에는 준수 서버의 기본 출력이 포함 되어 있습니다.

```XML
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

다음 코드 샘플에는 샘플 XSL 변환이 포함 되어 있습니다.

```XML
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
