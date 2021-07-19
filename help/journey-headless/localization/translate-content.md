---
title: Translate content
description: Use the translation connector and rules to translate your headless content.
---
# Translate Content {#translate-content}

Use the translation connector and rules to translate your headless content.

## The Story So Far {#story-so-far}

In the previous document of the AEM headless localization journey, [Configure Translation Rules](translation-rules.md) you learned how how to use AEM's translation rules to identify your translation content. You should now:

* Understand what the translation rules do.
* Be able to define your own translation rules.

Now that your connector and translations rules are set up, this article takes you through the next step of translating your headless content.

## Objective {#objective}

This document helps you understand how to use AEM's translation projects along with the connector and your translations rules to translate content. After reading this document you should:

* Understand what a translation project is.
* Be able to create new translation projects.
* Use translation projects to translate your headless content.

## Creating a Translation Project {#creating-translation-project}

Translation projects enable you to manage the translation of headless AEM content. A translation project contains the content to be translated into other languages.

When content is added to a translation project, a translation job is created for it. Jobs provide commands and status information that you use to manage the human translation and machine translation workflows that execute on the resources.

To create a translation project:

1. Navigate to **Navigation** -&gt; **Assets** -&gt; **Files**. Remember that headless content in AEM is stored as assets known as Content Fragments.
1. Select the language root of your project. In this case we have selected `/content/dam/wknd/en`.
1. Tap or click the rail selector and show the **References** panel.
1. Tap or click on **Language Copies**.
1. Check the **Language Copies** checkbox.
1. Expand the section **Update Language Copies** at the bottom of the references panel.
1. In the **Project** dropdown, select **Create Translation Project(s)**.
1. Provide an appropriate title for your translation project.
1. Tap or click **Start**.

![Create a translation project](assets/create-translation-project.png)

You receive a message that the project was created.

>[!NOTE]
>
>It is assumed that the necessary language structure for the translations languages have already been created as part of the [definition of your content structure.](getting-started.md#content-structure) This should be done in collaboration with the content architect.

## Using a Translation Project {#using-translation-project}

When creating the translation project, AEM evaluated the headless content under the path you selected as well as based on the rules that you previously defined. Based on those rules, it extracted the content that requires translation into a new translation project.

To view the translation project:

1. Navigate to **Navigation** -&amp; **Projects**.
1. Tap or click the project that was created in the previous section.

![Translation project](assets/translation-project.png)

The project is divided into multiple cards.

* **Summary** - This card shows the basic header information of the project including the owner, language, and translation provider.
* **Translation Job** - This card shows an overview of the actual translation job including the status, number of assets, etc.
* **Team** - This card shows the users who are collaborating on this translation project. This journey will not cover this topic.
* **Tasks** - Additional tasks associated with translating the content such as to do items or workflow items. This journey will not cover this topic.

To see the detail of the headless content included in this project:

1. Tap or click on the ellipsis button at the bottom of the **Translation Job** card.
1. The **Translation Job** window lists all items in the job.
![Translation Job detail](assets/translation-job-detail.png)
1. Tap or click a line to see the detail of that line, keeping in mind that one line may represent multiple content items to translate.
1. Tap or click the selection checkbox for a line item to see further options such as the option to delete it from the job or view it in the Content Fragments or Assets consoles.

![Translation Job options](assets/translation-job-options.png)

Typically the content for the translation job starts in the **Draft** state as indicated by the **State** column in the **Translation Job** window.

To start the translation job, return to the translation project overview and tap or click the chevron button at the top of the **Translation Job** card and select **Start**.

![Start translation job](assets/start-translation-job.png)

AEM now communicates with your translation configuration and connector to send the content to the translation service. You can view the progress of the translation by returning to the **Translation Job** window and viewing the **State** column of the entries.

![Translation Job approved](assets/translation-job-approved.png)

Machine translations automatically return with a state of **Approved**. Human translation allows for more interaction, but is beyond the scope of this journey.

## Reviewing Translated Content {#reviewing}

[As previously seen,](#using-translation-project) machine translated content flows back into AEM with the status of **Approved** since the assumption is that because machine translation is being used, no human intervention is required. However it is of course still possible to review the translated content.

Simply go to the completed translation job and select a line item by tapping or clicking the checkbox. The icon **Reveal in Content Fragment** is shown in the tool bar.

![Reveal in content fragment](assets/reveal-in-content-fragment.png)

Tap or click that icon to open the translated content fragment in its editor console to see the details of the translated content.

![A translated content fragment](assets/translated-content-fragment.png)

You can further modify the content fragment as necessary, providing you have the proper permission, but editing content fragments is beyond the scope of this journey. Please see the [Additional Resources](#additional-resources) section at the end of this document for more information on this topic.

The project's job is to collect all the resources related to a translation in one place for easy access and a clear overview. However as you can see by viewing the detail of a translated item, the translations themselves flow back into the asset folder of the translation language. In our example here

```text
/content/dam/wknd/es
```

If you navigate to this folder via **Navigation** -&gt; **Files** -&gt; **Assets**, you will see the translated content.

![Translated content folder structure](assets/translated-file-content.png)

AEM's translation framework receives the translations from the translation connector and then automatically creates the content structure based on the language root and using the translations provided by the connector.

It is important to understand that this content is not published. It remains on the authoring instance of AEM until you decide it is ready to be publish. We will see how to do this in the next step of the localization journey.

## Human Translation {#human-translation}

If your translation service provides human translation, the review process offers more options. For example, translations arrive back in the project with the status **Draft** and must be reviewed and approved or rejected manually.

Human translation is beyond the scope of this localization journey. Please see the [Additional Resources](#additional-resources) section at the end of this document for more information on this topic.

## What's Next {#what-is-next}

Now that you have completed this part of the headless localization journey you should:

* Understand what a translation project is.
* Be able to create new translation projects.
* Use translation projects to translate your headless content.

Build on this knowledge and continue your AEM headless localization journey by next reviewing the document [Publish translated content](publish-content.md) where you will learn how to publish your translated content and how to update those translations as your language root content changes.

## Additional Resources {#additional-resources}

While it is recommended that you move on to the next part of the headless localization journey by reviewing the document [Publish translated content,](publish-content.md) the following are some additional, optional resources that do a deeper dive on some concepts mentioned in this document, but they are not required to continue on the headless journey.

* [Managing Translation Projects](/help/sites-cloud/administering/translation/managing-projects.md) - Learn the details of translation projects and additional features such as human translation workflows and multi-language projects.