# testRNA
##Obtaining data
# path/10X/ contains a directory for each of the expriments, each with the three 10X files.
dirs = dir(paste0(path,'/10X'),full.names=T)
tenx = Combine.Multiple.10X.Datasets(dirs,random.sample=1000,min.genes=200)
singler = CreateSinglerSeuratObject(tenx$sc.data, tenx$orig.ident, 'Zheng', 
                                    variable.genes='de',regress.out='nUMI', 
                                    technology='10X', species='Human', 
                                    citation='Zheng et al.', reduce.file.size = F, 
                                    normalize.gene.length = F)
save(singler,file='10x (Zheng) - 10000cells.RData'))
