# Abalign Manual

- [Introduction](#Introduce)
- [Setup](#Setup)
- [Usage](#Usage)

  - [Software constitution](#Software_constitution)

    - [Executable file (UI)](#Executable_file)
    - [lib folder](#lib_folder)

  - [Basic functions](#Basic_functions)

    - [File input](#File_input)
    - [Numbering strategy](#Numbering_strategy)
    - [multiple sequence alignment](#mutil_sequence_alignment)
    - [File Save](#File_save)
    - [Terminate process](#Terminate)

  - [Option function](#Option_function)

    - [Hierarchical clustering](#Hierarchical_clustering)
    - [Phylogenetic tree](#Phylogenetic_tree)
    - [Interface screenshot](#Interface_screenshot)
    - [Character Search](#Character_Search)

  - [Menu bar](#Menu_bar)

    - [Display](#Display)

      - [Remove duplication](#Remove_duplication)
      - [Sequence filtering](#Sequence_filtering)
      - [Select the display area](#Select_the_display_area)

    - [Tools](#Tools)

      - [Find V Gene](#Find_V_Gene)
      - [Heatmap](#Heatmap)
      - [Seqlogo](#Seqlogo)
      - [Abundance map](#Abundance_map)

    - [Parameter](#Parameter)

- [Example](#Example)
- [Notice](#Notice)
- [Reference](#Reference)

**Introduce**

Multiple sequence alignment has long been used as a powerful tool to investigate the evolutionary, structural and functional properties of protein families. It is also a fundamental technique in recent deep-learning based protein 3D structure prediction methods. The existing multiple sequence alignment methods are extremely difficult to align the highly variable regions of antibody or B-Cell Receptor (BCR) sequences without the prior knowledge of antibody gene recombination and hypermuation in the process of maturation. This multiple sequence alignment tool, named Abalign, which integrates heuristic knowledge of the standardized antibody sequence numbering schemes, including IMGT, KABAT and Chothia systems. The alignment follows the well-characterized patterns of the conserved or highly variable positions known by immunology studies. Hence the alignment result is consistent with the structural and immunological knowledge. Abalign was implemented in a user-friendly software with interactive and visual interface, which supports the multiple sequence alignment, as well as sequence clustering, antibody numbering, CDR delimiting, constructing phylogenetic tree, sequence similarity heat map, V-gene determination and abundance analysis by just clicking the buttons. Abalign allows the high-thoughput analysis for BCR sequencing data, which can be finished in 850 minutes for1 Gb DNA fasta sequences. Abalign is a powerful and efficient tool for biological researchers to analyze massive amounts of BCR or antibody sequences and get new discovery in immunoinformatic study.

**Setup** **(for windows)**

Double click **Align Setup.exe** to enter the installation, click **Browse** to select the installation path, and click **Next**.

![](RackMultipart20211218-4-ozz18x_html_a3b5d609f43b21e.png)

Select whether to **Create a desktop shortcut** , click **Next** , and click **Install** to install.

![](RackMultipart20211218-4-ozz18x_html_d6c2c0b0b07a266e.png)

![](RackMultipart20211218-4-ozz18x_html_72f2765d582dbfac.png)

Please wait for the installation to complete, select whether to **Launch Abalign** , and click **Finish** to exit the installation program.

![](RackMultipart20211218-4-ozz18x_html_28495fb64e24bb33.png)

If you need to uninstall the software, click **unins000.exe** under the installation folder or uninstall or change the program through windows to complete the uninstall.

**Usage**

**Software constitution**

**Note: Do not modify any content of lib folder**

**Executable file (UI)**: The file named Abalign\_ui in the software root directory is the visual window program, double-click to run.

**lib folder** : Do not make any changes to the lib folder under the software directory, which contains a series of configuration files and binary files that implement multiple sequence alignment.

**example folder** : The sequence files of DNA and amino acids in FASTA format are stored for user testing.

**Basic functions**

**File input:** The program supports the amino acid sequence file or nucleic acid sequence file in FASTA format. The input file can be selected by clicking the **Input** button or dragged directly into the text box to input the file.

**Numbering strategy:** Select the antibody numbering strategy ( support Chothia, Kabat, IMGT strategy ) and the type of antibody sequence by clicking the &quot; **I**** MGT **** for heavy chain**&quot; drop-down menu ( select the heavy chain will detect all the antibody heavy chains in the input sequence and filter out the light chain and the non-variable region sequence, the light chain is the same )

**Multi**** ple **** sequence alignment: **Click the** Align**button to find the variable domain of the antibody and use sequences to execute multiple sequence alignment. During the alignment, the V Gene and the species that are most similar to each variable region sequence are found, and the V Gene name and species name are displayed after the corresponding sequence name. After running, the residue number of each site will be displayed above, and the seven regions of the antibody variable domain (FR1, CDR1... CDR3, FR4) are rendered into different colors by default. If you need to change the rendering method, please click**Display- \&gt; Sequence render mode**.

Figure 1. Multiple sequence alignment results. ![](RackMultipart20211218-4-ozz18x_html_ff498ae256601e45.png)

**File Save:** Click the **Save** button to save the contents of the current interface as .fasta file and .temp file. The former stored the multiple sequence alignment results and the latter stored the multiple sequence alignment results with &#39;\*&#39; as a separation of the various regions in the variable region.

**Terminate process:** Click the **Cancel** button to terminate the ongoing multiple sequence alignment.

**Optional functions**

**Note: All optional functions require multi-sequence alignment first.**

**Hierarchical clustering:** Click the **Cluster** button to run hierarchical clustering. This function will hierarchically cluster the multiple sequence alignment data after Align. After the clustering, the hierarchical clustering tree will be displayed. The sequence will be rearranged according to the tree, and the same sequence will be arranged adjacently, and the sequence name will be rendered as the same color. The parameters of hierarchical clustering can be changed by the **Parameter** option in the menu bar.

Fig. 2. Hierarchical clustering results of antibody variable d ![](RackMultipart20211218-4-ozz18x_html_ea1394160b67cae6.png)
 omain

**Phylogenetic tree:** This function uses [FastTree](http://www.microbesonline.org/fasttree/) software ( maximum likelihood method )[1]to build .nwk file and visualize it with [Ete3](http://etetoolkit.org/). After clicking **Phylogeny** , the parameter box of the phylogenetic tree will be popped up. After clicking **Run** , the phylogenetic tree will be constructed. The text box below will enter the log information. Visualization results of the phylogenetic tree appear after running. If you need to save the .nwk file of the current phylogenetic tree, click the **Save** button below the parameter box to save.

F ![](RackMultipart20211218-4-ozz18x_html_49e12be071215f7e.png) ig. 3. Parameter panel of phylogenetic tree

1. Maximum likelihood model : Maximum likelihood model for amino acid substitutions, including WAG, JJT, LG
2. Test of Phylogeny : branch checking methods for phylogenetic trees, including Shiodaira Hasegawa Text(defined by FastTree) and Bootstrap(1000x)
3. Searching for best join : Using the neighbor-join method to construct a rough tree topology of the system, the default [relaxed neighbor joining](https://pubmed.ncbi.nlm.nih.gov/16752216/) is faster, the exhaustive search is slower, and the search of the visible set is only the fastest
4. Join option : The neighbor-join method used to construct a rough topology, defaulting to neighbor - join, in addition to BioNJ.
5. Show msa : the results of multi-sequence alignment will be displayed with the evolution tree.
6. Sequences Selection: By default, All sequences in the class, the system tree is constructed with all sequences currently displayed, Sequences belong to a specific V Gene, and the system tree is constructed with sequences belonging to V Gene selected in V Gene Selection.
7. V Gene Selection: The option contain the V Gene types of all sequences on the current page. Availabled When option of &quot;Sequences Selection&quot; switch to &quot;Sequences belong to a specific V Gene&quot;,

![](RackMultipart20211218-4-ozz18x_html_bb91aca16b4dec96.png)

Figure 4. Visualization results of system tree constructed according to V Gene

![](RackMultipart20211218-4-ozz18x_html_f1654335565008f9.png)

Fig 5. Phylogenetic tree with multiple sequence alignment results

In this program, the root node is automatically set to the sequence most similar to the germline V Gene in all sequences of the phylogenetic tree, and the germline V Gene is the V Gene of the most abundant sequence. The red branch in the tree represents the evolutionary path from the root node to the sequence with the highest abundance. The program renders the label of leaf nodes by the abundance of sequences. The higher the proportion of the number of sequences of leaf nodes in the total number of sequences of all leaf nodes is, the closer the color of leaf node label is to red and the larger the font is.

**Interface screenshot:** Click the **Screensho**** t** button to save the result screenshot, which is in .png format by default. Note: Too many sequences may not be successful.

**Character Search:** Enter the string you want to query in the text box after the **Search** button. Click the **Search** button to search for the location of the string in the sequence name and sequence.

**Menu bar**

**Display**

![](RackMultipart20211218-4-ozz18x_html_2d289c7b6fb4e738.png)

Fig 6. Display options

**Remove duplication:** By default, repeats in the variable region sequence of the antibody are removed during Align.

**Sequence filtering:**&quot; **Normal**&quot; is defaulted. After selecting &quot; **Normal**&quot; or &quot; **Strict**&quot;, the length of each region in the variable region of the antibody will be limited in the Align process. After selecting &quot; **Off**&quot;, the restriction will be closed. If it is not within the limit, the sequence will be filtered out. &quot;Strict&quot; is more restrictive than &quot;Normal&quot;.

**Switch sequence rendering mode** : Click &quot; **Display**&quot; and move the mouse over &quot; **Sequence color mode**&quot;, &quot; **Light mode**&quot;(more vivid colour) and &quot; **soft mode**&quot; (more soft colour) can be selected. Click &quot; **Display**&quot;, move the mouse to &quot; **Sequence render mode**&quot;, and select &quot; **Color by region**&quot;(different regions of the antibody sequence rendered as different colours) and &quot; **Color by amino**&quot;(different amino acids rendered as different colours).

**Select the display area:** click &quot; **Display**&quot;, select Display full msa ( default ) to display the entire msa results; move the mouse to the &quot; **Display by region**&quot;, you can choose to display different regions of the antibody ; click &quot; **Display by cluster**&quot; ( after complete the cluster operation ) to select the class that needs to be displayed by pop-up the tab.

Figure 7. Display only the CDR1, CDR2, CDR3 regions of the antibody variable d ![](RackMultipart20211218-4-ozz18x_html_410078e61ee0e42.png)
 omain

**Tools**

**Find V Gene:** The default selection cannot be changed to find the most similar V Gene for each sequence of antibody variable domain and the species to which the V Gene belongs, and display the V Gene name and the species name behind the corresponding sequence name.

**Heatmap:** Click on &quot; **Heatmap**&quot; to generate a heatmap based on the similarity of the current sequence, and you can cluster the heatmaps and wait for a while if the number of sequences is large. All Heatmaps are based on the content of the current multi-sequence alignment text box. If &quot;Display&quot; is used to change the current displayed sequence, Heatmap will change accordingly.

F ![](RackMultipart20211218-4-ozz18x_html_85d89b17ab592861.png)
 igure 8. Heatmap after hierarchical clustering

**S ![](RackMultipart20211218-4-ozz18x_html_d8f61a67dd394747.png)
 eqlogo: **Click** Tools **, move the mouse to &quot;** Seqlogo **&quot;, click &quot;** By Entropy **&quot; to get entropy ordinate Seqlogo, click &quot;** By Frequence **&quot; to get frequency ordinate Seqlogo. Move the mouse to the &quot;** Color**&quot; option to change the rendering mode of Seqlogo. All Seqlogo is based on the content of the current multiple sequence alignment text box. If Display is used to change the current displayed sequence, Seqlogo will change accordingly. To ensure compatibility, all Seqlogo is in PDF format.

Figure 9. Seqlogo for the entire antibody variable region, with entropy as the y-axis

**Abundance map:** Click &quot; **Tools**&quot;, move the mouse to &quot; **Abundance**&quot;, see &quot; **V Gene abundance**&quot; and &quot; **Sequence abundance**&quot; options, and generate V Gene abundance and Sequence abundance maps after clicking.

Figure 10. V Gene abundance map Figure 11. Sequence abundance map ![](RackMultipart20211218-4-ozz18x_html_85858589c7f9561c.png)
 ![](RackMultipart20211218-4-ozz18x_html_570e798ad20e0851.png)

**Parameter**

After clicking the &quot; **Parameter**&quot; in the menu bar, a dialog box will pop up, which can modify the clustering penalty, clustering weight ( if the weight of CDR3 region is increased, the similarity of CDR3 region will be paid more attention to in the clustering process ) and the parameters of Hierarchical Clustering Dendrogram.

F ![](RackMultipart20211218-4-ozz18x_html_8ac9c6c7425539db.png) igure 12. Hierarchical Clustering Dendrogram parameters

1. Branch: It represents the number of branches displayed in hierarchical clustering tree. This parameter takes effect with truncate\_mode parameter.

(b) Threshold: represents the threshold of clustering partition. If this value is 0.1, a tenth of the total length of the Y-axis (the maximum difference between sequences) is used as a threshold to partition different classes. The more the number of clusters, the smaller the value should be set.

(c) leaf \_ font: Represents the size of the branch label font

(d) cluster\_method: represents the method used to calculate the distance between two classes during clustering.

(e) root\_orientation: Represents the direction of the root.

(f) count\_sort: indicates whether the clustering results are sorted according to the number of each category.

(g) Distance\_sort: indicates whether the clustering results are sorted according to the distance of each category.

**Example**

In this case, we used the samples obtained from single cell sequencing of patients with new coronavirus for demonstration.

**Step 1 Input file:** select the fasta file that needs to be processed after clicking Input.

**Step 2 Search for antibody variable domain and multiple sequence alignment:** After file loading is completed, click &quot;Align&quot; to run the program, the progress bar below the program will show the progress of the program, if the file is too large, the progress bar is not updated in a short time is normal. After the comparison, a dialog box will be popped, and the total number of input sequences will be displayed in the dialog box. The number of sequences in the variable region of the antibody and the number of sequences after deduplication will be detected.

![](RackMultipart20211218-4-ozz18x_html_2914a571d6dd74af.png)

**S ![](RackMultipart20211218-4-ozz18x_html_8893c74547d25cda.png)
 ![](RackMultipart20211218-4-ozz18x_html_9ce90f97e92f5041.png)
 tep 3 looks at multiple sequence alignments:** click the &quot;Tools&quot; button in the top menu bar and move the mouse to &quot;Abundance&quot;. Click &quot;V Gene abundance&quot; or &quot;Sequence abundance&quot; to obtain the abundance map of V Gene and sequence. Somatic hypermutation occur during antibody maturation and the final mature antibody is highly expressed in the body. Therefore, it is meaningful to study antibodies with high abundance.

**Step 4 Build the phylogenetic tree:** according to the sequence abundance information, build the tree with the V Gene of the high abundance sequence. In this case, the most abundant sequence belongs to V Gene &quot;IGVH3-53 \* 01&quot;. Click Phylogeny to open the parameter list of tree building, switch the Sequences Selection option to &quot;Sequences belonging to a specific V Gene&quot;, select &quot;IGVH3-53 \* 01&quot; in the V Gene Selection option, and click Run to start building the evolutionary tree. If you are satisfied with the tree building results, click the &quot;Save the current Nwk file&quot; button in the tree building menu to save the .nwk file of the current system tree.

![](RackMultipart20211218-4-ozz18x_html_c25ea49446cb3f3b.png)

**Step 5 View the phylogenetic tree:** Once the evolution tree is built, a visual window pops up that adjusts the view and displays other information about the tree through the button above the visual window. After selecting the node of the tree, you can also modify the attributes of the node, such as the color of the node, in the right window.

![](RackMultipart20211218-4-ozz18x_html_a640993b0c0674b4.png)

**S ![](RackMultipart20211218-4-ozz18x_html_ada4ebc44d144ae1.png)
 tep 6 Hierarchical clustering:** After clicking Cluster, hierarchical clustering can be carried out. If the file is too large, it will consume more time, please wait patiently. After the clustering, the hierarchical clustering tree graph will be displayed. Multiple sequence alignment will be rearranged according to the results of the tree graph, and the sequence name will be rendered as the same color according to the color of the branch of the tree graph. After the clustering is completed, click Display- \&gt; Display by cluster in the menu bar to select the class that needs to be displayed.

**Step 7 Building phylogenetic trees with different classes:** After selecting one or more classes that need to be used to build trees in Display by cluster, click Phylogeny again, adjust &quot;Sequences Selection&quot; to &quot;All sequences in the class&quot;, and click Run to build phylogenetic trees.

![](RackMultipart20211218-4-ozz18x_html_212bb43e43efaec0.png)

**Notice**

1. If there is no response during the operation of the program, wait a little and the program is still running.
2. Multiple sequence alignment is for input files. If multiple sequence alignment is carried out, then multiple sequence alignment is carried out again, or multiple sequence alignment is carried out for input files, rather than after alignment.
3. Clicking the Cancel button can only terminate the alignment process and cannot be canceled by Cancel when the alignment sequence is finally loaded.
4. Hierarchical clustering consumes resources and time. To hierarchically cluster a large number of sequences, ensure that the computer has sufficient memory.
5. If the software screen is not displayed properly, adjust the scale of the screen.

This software is developed by Yang Cao Laboratory, College of Life Sciences, Sichuan University. The main developers are Fanjie Zong, Chenyu Long, Wanxin Hu, and Yang Cao. If you have any opinions or suggestions, please contact [cy\_scu@yeah.net](mailto:cy_scu@yeah.net).

**Reference**

1. Price MN, Dehal PS, Arkin AP. FastTree: computing large minimum evolution trees with profiles instead of a distance matrix[J]. Mol Biol Evol. 2009 Jul;26(7):1641-50.
